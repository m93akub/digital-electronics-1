# Lab 6: Michal Kubant

### Bidirectional counter

1. Listing of VHDL code of the completed process `p_cnt_up_down`. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
    p_cnt_up_down : process(clk)
    begin
        if rising_edge(clk) then
            if (reset = '1') then
                s_cnt_local <= (others => '0');
            elsif (en_i = '1') then
                if(cnt_up_i = '1') then
                    s_cnt_local <= s_cnt_local + 1;
                else
                    s_cnt_local <= s_cnt_local - 1;
                end if;
            end if;
        end if;
    end process p_cnt_up_down;
```

2. Screenshot with simulated time waveforms. Test reset as well. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![waveforms](https://user-images.githubusercontent.com/99811894/160666401-df5316cb-df20-4a4f-8019-55bb71788b1f.png)

### Two counters

1. Image of the top layer structure including both counters, ie a 4-bit bidirectional counter from *Part 4* and a 16-bit counter with a 10 ms time base from *Experiments on your own*. The image can be drawn on a computer or by hand. Always name all inputs, outputs, components and internal signals!

   
