# Implementation of  8 bit Subtractor
**code ( Dataflow )**

entity eightbit_sub is
    Port (
        A : in STD_LOGIC_VECTOR (7 downto 0);
        B : in STD_LOGIC_VECTOR (7 downto 0);
        D : out STD_LOGIC_VECTOR (7 downto 0);
    )
end eightbit_sub;

begin
    D(7 downto 0) <= A(7 downto 0) - B(7 downto 0);

**Text-Bench**

A <= "00000000"; B <= "00000000"; -> 00000000
A <= "00000010"; B <= "00000001"; -> 00000001
A <= "10000000"; B <= "00000001"; -> 01111111



