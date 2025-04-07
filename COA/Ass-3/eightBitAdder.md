# Implementation of  8 bit Adder
- code ( Dataflow )

entity eightbit_adder is
    Port (
        A : in STD_LOGIC_VECTOR (7 downto 0);
        B : in STD_LOGIC_VECTOR (7 downto 0);
        C : out STD_LOGIC_VECTOR (7 downto 0);
    )
end eightbit_adder;

begin
    C(7 downto 0) <= A(7 downto 0) + B(7 downto 0);

**Text-Bench**

A <= "00000000"; B <= "00000000"; -> 00000000
A <= "00000001"; B <= "00000001"; -> 00000010
A <= "11111111"; B <= "00000001"; -> 00000000
