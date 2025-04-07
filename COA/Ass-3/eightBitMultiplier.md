# Implementation of  8 bit Multiplier
**code ( Dataflow )**

entity eightbit_mul is
    Port (
        A : in STD_LOGIC_VECTOR (7 downto 0);
        B : in STD_LOGIC_VECTOR (7 downto 0);
        C : out STD_LOGIC_VECTOR (15 downto 0);
    )
end eightbit_mul;

begin
    C(15 downto 0) <= A(7 downto 0) * B(7 downto 0);

**Text-Bench**

A <= "00000000"; B <= "00000000"; -> 0000000000000000
A <= "00000001"; B <= "00000001"; -> 0000000000000001
A <= "00000010"; B <= "00000010"; -> 0000000000000100
