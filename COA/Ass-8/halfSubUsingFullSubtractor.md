# Half Subtractor Using Full Subtractor (Structural Method)

**STEP - 1 | "First make a half subtractor" 
**STEP - 2 | "Then make a OR Gate" 
**STEP - 3 | "Finally copy the entity portion from previous 2 files and write the main logic"

**Code**

step - 1 code
begin
Diff <= A xor B;
Bout <=  (not A) and B;
-------------------------
-------------------------
step - 2 code
begin
C <= A or B;
-------------------------
-------------------------
step - 3 code
signal D1 , B1 , B2 : STD_LOGIC;

begin
m0 : [half_adder_file_ka_name] port map(A , B , D1 , B1);
m1 : [half_adder_file_ka_name] port map(D1 , Bin , Diff , B2);
m2 : [Or_gate_file_ka_name] port map(B1, B2 , Bout);

**Text Bench**
A <= '0' ; B <= '0' ; Bin <= '0';
A <= '1' ; B <= '1' ; Bin <= '1';
