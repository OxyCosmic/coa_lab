# Binary To Gray

**code(Behavioral)**

entity binary_to_gray is
    Port (
        B : in STD_LOGIC_VECTOR(3 downto 0);
        G : out STD_LOGIC_VECTOR(3 downto 0);
    );

begin 
Process(B)
begin
G(3) <= B(3);
for i in 2 downto 0 loop
if (B(i+1) = B(i)) then
G(i) <= '1';
else
G(i) <= '0';
end if;
end loop;
end Process;

**Text Bench**
B <= "0000"; WAIT FOR 10 ns; 
B <= "0001"; WAIT FOR 10 ns; 