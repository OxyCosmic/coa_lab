# 4 bit parallel adder
**code (Behavioral)**
entity Parallel_Adder4Bit is
    Port (
        A : in STD_LOGIC_VECTOR ( 3 downto 0);
        B : in STD_LOGIC_VECTOR ( 3 downto 0);
        Cin : in STD_LOGIC;
        Sum : out STD_LOGIC_VECTOR ( 3 downto 0);
        Cout : out STD_LOGIC;
    )
end Parallel_Adder4Bit;

begin
Process(A , B , Cin)
Variable u: std_logic_vector(4 downto 0);
begin
u(0) := Cin;
u(0) := '0';
for i in 0 to 3 loop
Sum(i) <= A(i) xor B(i) xor u(i);
u(i+1) := (A(i) and B(i)) or (B(i) and u(i)) or (u(i) and A(i));
end loop;
Cout <= u(4);
end Process;

**Text Bench**
A <= "0101"; B <= "0011"; Cin <= '0';
A <= "0111"; B <= "1000"; Cin <= '0';
A <= "1111"; B <= "0001"; Cin <= '0';
