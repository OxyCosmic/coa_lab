# 3:8 Decoder

**Code (Behavioral)**

entity threeEightDecoder is
    Port (
        inp : in STD_LOGIC_VECTOR ( 2 downto 0);
        oup : out STD_LOGIC_VECTOR ( 7 downto 0);
    );

end threeEightDecoder;

begin
Process(inp)
begin
case inp is
    when "000" => oup <= "00000001";
    when "001" => oup <= "00000010";
    when "010" => oup <= "00000100";
    when "011" => oup <= "00001000";
    when "100" => oup <= "00010000";
    when "101" => oup <= "00100000";
    when "110" => oup <= "01000000";
    when "111" => oup <= "10000000";
    when others => oup <= "XXXXXXXX";
end case;
end Process;

**Code (DataFlow)**

entity threeEightDecoder is
    Port (
        inp : in STD_LOGIC_VECTOR ( 2 downto 0);
        oup : out STD_LOGIC_VECTOR ( 7 downto 0);
    );

end threeEightDecoder;

begin
Process(inp)
variable s : integer;
begin
s := conv_integer(inp);
for i in 0 to 7 loop
if (i = s) then
oup(i) <= '1';
else
oup(i) <= '0';
end if;
end loop;
end Process;

**Text Bench**
inp <= "000";
inp <= "100";
inp <= "111";