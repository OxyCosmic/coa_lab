# 2:4 decoder
**code (Behavioral)**

entity twoFourDecoder is
     Port(
        sel : in STD_LOGIC_VECTOR(1 downto 0);
        outp : out STD_LOGIC_VECTOR(3 downto 0);
     );
end twoFourDecoder;

begin
Process(sel)
begin
case sel is
    when "00" =>outp<= "0001";
    when "01" =>outp<= "0010";
    when "10" =>outp<= "0100";
    when "11" =>outp<= "1000";
    when others =>outp<= "XXXX";
end case;
end Process;

**Text Bench**
sel <= "00";
sel <= "11";