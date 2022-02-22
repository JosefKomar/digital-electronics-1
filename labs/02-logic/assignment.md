# Lab 2: Josef Komar

### 2-bit comparator

1. Karnaugh maps for other two functions:

   Greater than:

   ![K-maps](images/kmap_BgreaterA.png)

   Less than:

   ![K-maps](images/kmap_BlessA.png)

2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

   ![Logic functions](images/comparator_min.png)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **230271**

```vhdl
    p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case ...
        s_b <= "0111"; s_a <= "0001"; wait for 100 ns;
        -- ... and its expected outputs
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        -- If true, then do not report anything
        report "Input combination 0111, 0001 FAILED" severity error;



        -- WRITE OTHER TEST CASES HERE
		  s_b <= "1111"; s_a <= "1111"; wait for 100 ns;
		  assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '1') and
                (s_B_less_A    = '0'))
        report "Input combination 1111, 1111 FAILED" severity error;  
         
         s_b <= "0100"; s_a <= "1001"; wait for 100 ns;
		   assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
         report "Input combination 0100, 1001 FAILED" severity error;

        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait; -- Data generation process is suspended forever
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![console](images/textconsole.png)

3. Link to your public EDA Playground example:

   [PC2 EDA Playground link](https://www.edaplayground.com/x/D92c)