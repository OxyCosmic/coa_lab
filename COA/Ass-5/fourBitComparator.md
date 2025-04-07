# 4 bit comparator

**Code (Behavioral)**
entity fourBitComp is
    Port (
        A : in STD_LOGIC_VECTOR(3 downto 0);
        B : in STD_LOGIC_VECTOR(3 downto 0);
        G : out STD_LOGIC;
        E : out STD_LOGIC;
        L : out STD_LOGIC;
    );
end fourBitComp;

begin
process(A , B)
begin
if ( A > B ) then
  G <= '1';
  E <= '0';
  L <= '0';
elsif ( A = B ) then
  G <= '0';
  E <= '1';
  L <= '0';
else
  G <= '0';
  E <= '0';
  L <= '1';
end if;
end Process;

**Text Bench**

A <= "0000"; B <= "0000";
A <= "1000"; B <= "0000";
A <= "0000"; B <= "1000";