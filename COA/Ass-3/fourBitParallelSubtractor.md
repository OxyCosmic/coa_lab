# 4 bit parallel subtractor
**code (Behavioral)**
entity Parallel_Sub4Bit is
    Port (
        A : in STD_LOGIC_VECTOR ( 3 downto 0);
        B : in STD_LOGIC_VECTOR ( 3 downto 0);
        Bin : in STD_LOGIC;
        Diff : out STD_LOGIC_VECTOR ( 3 downto 0);
        Bout : out STD_LOGIC;
    );
end Parallel_Sub4Bit;

begin
Process(A , B , Bin)
Variable u: std_logic_vector(4 downto 0);
begin
u(0) := Bin;
u(0) := '0';
for i in 0 to 3 loop
Diff(i) <= A(i) xor B(i) xor u(i);
u(i+1) := (not A(i) and B(i)) or (B(i) and u(i)) or (u(i) and not A(i));
end loop;
Bout <= u(4);
end Process;

**Text Bench**
A <= "0101"; B <= "0011"; Bin <= '0';
A <= "1000"; B <= "0100"; Bin <= '0';
A <= "0010"; B <= "0110"; Bin <= '0';
