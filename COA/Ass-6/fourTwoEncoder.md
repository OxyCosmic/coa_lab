# 4:2 encoder
**Code (Case)**

entity fourTwoEncoder is
    Port (
        inp : in STD_LOGIC_VECTOR(3 downto 0);
        oup : out STD_LOGIC_VECTOR(1 downto 0);
    );
end fourTwoEncoder;

begin
Process(inp)
begin
case inp is
when "0001" => oup <= "00";
when "0010" => oup <= "01";
when "0100" => oup <= "10";
when "1000" => oup <= "11";
when others => oup <= "XX";
end case;
end Process;

**Text Bench**
inp <= "0001";
inp <= "0010";
inp <= "0100";
