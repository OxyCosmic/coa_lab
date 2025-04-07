# 8:3 encoder
**Code (Case)**

entity eightThreeEncoder is
    Port (
        inp : in STD_LOGIC_VECTOR(7 downto 0);
        oup : out STD_LOGIC_VECTOR(2 downto 0);
    );
end fourTwoEncoder;

begin
Process(inp)
begin
for x in 0 to 7 loop
if (inp(x) = '1') then
    oup <= Conv_Std_Logic_Vector(x,3);
end if;
end loop;
end Process;

**Text Bench**
inp <= "00000001";
inp <= "00000010";
inp <= "00000100";
