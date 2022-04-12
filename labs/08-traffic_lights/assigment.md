# Lab 8: YOUR_FIRSTNAME LASTNAME

### Traffic light controller

1. Figure of state diagram:

   ![IMG_20220412_224503](https://user-images.githubusercontent.com/99811894/163052504-e47f41df-11f9-466d-8e40-434e29008880.jpg)

2. Listing of VHDL code of the completed process `p_traffic_fsm`. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
    p_traffic_fsm : process(clk)
    begin
        if rising_edge(clk) then
            if (reset = '1') then   -- Synchronous reset
                s_state <= STOP1;   -- Set initial state
                s_cnt   <= c_ZERO;  -- Clear delay counter

            elsif (s_en = '1') then
                case s_state is
                
                    when STOP1 =>
                        -- Count up to c_DELAY_1SEC
                        if (s_cnt < c_DELAY_1SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            -- Move to the next state
                            s_state <= WEST_GO;
                            -- Reset local counter value
                            s_cnt <= c_ZERO;
                        end if;

                   when WEST_GO =>
                        if (s_cnt < c_DELAY_4SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <=WEST_WAIT;
                            s_cnt <= c_ZERO;    
                        end if;

                    when WEST_WAIT =>   
                        if (s_cnt < c_DELAY_2SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <= STOP2;
                            s_cnt <= c_ZERO;    
                        end if;
                        
                     when STOP2 =>   
                        if (s_cnt < c_DELAY_1SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <= SOUTH_GO;
                            s_cnt <= c_ZERO;    
                        end if;    
                        
                     when SOUTH_GO =>   
                        if (s_cnt < c_DELAY_4SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <= SOUTH_WAIT;
                            s_cnt <= c_ZERO;    
                        end if;  
                      
                      when SOUTH_WAIT =>
                        if (s_cnt < c_DELAY_2SEC) then
                            s_cnt <= s_cnt + 1;
                        else
                            s_state <=STOP1;
                            s_cnt <= c_ZERO;    
                        end if;

                      when others =>
                        s_state <= STOP1;
                        s_cnt   <= c_ZERO;
                end case;
            end if; -- Synchronous reset
        end if; -- Rising edge
    end process p_traffic_fsm;
```

3. Screenshot with simulated time waveforms. The full functionality of the entity must be verified. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   ![waveforms](https://user-images.githubusercontent.com/99811894/163045321-6f404b7a-912f-454d-9a35-eaafbb60f80a.png)

### Smart controller

1. State table for smart controller using two sensors and two traffic lights in three colors.
