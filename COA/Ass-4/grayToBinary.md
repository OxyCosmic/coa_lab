# Gray To Binary

**code(Behavioral)**

entity gray_to_binary is
    Port (
        G : in STD_LOGIC_VECTOR(3 downto 0);
        B : inout STD_LOGIC_VECTOR(3 downto 0);
    );

begin 
Process(G , B)
begin
B(3) <= G(3);
for i in 2 downto 0 loop
if (G(i) = B(i+1)) then
B(i) <= '1';
else
B(i) <= '0';
end if;
end loop;
end Process;

**Text Bench**
G <= "0000";
G <= "1111";