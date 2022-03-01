# Lab 2: Michal Kubant

### 2-bit comparator

1. Karnaugh maps for other two functions:
   Greater than:
 ![greater](https://user-images.githubusercontent.com/99811894/156231096-916cad29-a90d-4e08-b56c-cc3b71d8a467.png)
 
   Less than:
![less](https://user-images.githubusercontent.com/99811894/156231057-87744138-11bf-41d0-a723-636527679322.png)
 
2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.
![eqations](https://user-images.githubusercontent.com/99811894/156231266-74b04c44-b50c-4f0b-95cf-fbfeffe58d37.svg)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: ****08

```vhdl
    p_stimulus : process
    begin
        -- Report a note at the begining of stimulus process
    	report "Stimulus process started" severity note;


    	-- ID: xxxx08
    	s_b <= "0000"; s_a <= "1000"; wait for 100 ns;
    	-- Expected output
    	assert ((s_B_greater_A = '0') and (s_B_equals_A = '0') and (s_B_less_A = '1'))
    	-- If false, then report an error
    	report "Test failed for input combination: 0000, 1000" severity error;

	    -- 1 (error msg)
    	s_b <= "0000"; s_a <= "0001"; wait for 100 ns;
    	-- Expected output
    	assert ((s_B_greater_A = '0') and (s_B_equals_A = '1') and (s_B_less_A = '0'))
    	-- If false, then report an error
    	report "Test failed for input combination: 0000, 0001" severity error;
     
    	-- 2
    	s_b <= "0000"; s_a <= "0010"; wait for 100 ns;
    	-- Expected output
    	assert ((s_B_greater_A = '0') and (s_B_equals_A = '0') and (s_B_less_A = '1'))
    	-- If false, then report an error
    	report "Test failed for input combination: 0000, 0010" severity error;
     
    	-- 3
    	s_b <= "0000"; s_a <= "0011"; wait for 100 ns;
    	-- Expected output
    	assert ((s_B_greater_A = '0') and (s_B_equals_A = '0') and (s_B_less_A = '1'))
    	-- If false, then report an error
    	report "Test failed for input combination: 0000, 0011" severity error;
      
    	-- eq
    	s_b <= "0001"; s_a <= "0001"; wait for 100 ns;
    	-- Expected output
    	assert ((s_B_greater_A = '0') and (s_B_equals_A = '1') and (s_B_less_A = '0'))
    	-- If false, then report an error
    	report "Test failed for input combination: 0001, 0001" severity error;

    	-- Report a note at the end of stimulus process
    	report "Stimulus process finished" severity note;
    	wait;
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![image](https://user-images.githubusercontent.com/99811894/156243678-8e54ec80-f188-410b-a362-acef462b9542.png)

3. Link to your public EDA Playground example:

   [https://www.edaplayground.com/...](https://www.edaplayground.com/...)
