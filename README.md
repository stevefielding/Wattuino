# Wattuino
Removed majority of the project. What remains is the Optiboot loader, which has been modified to work with
a multi node RS485 network. Uses a sync word to identify each node and requires a modified avrdude to 
send the appropriate sync word.
[avrdude_rs485](https://github.com/stevefielding/avrdude_rs485)  
There is a python helper script which performs the power cycle and runs avrdude.  
[pod_prog](to be completed)  
The process for loading new user code is:  
1. Power cycle the ATMega
2. You should see the LED blink fast.
3. You now have 8s to program the new code.
4. Run pod_prog or avrdude directly, to program the new file.
5. Immediately that the programming is complete, the ATmega should run the new code.  
Note that there is always an 8s delay for booting user code. This is because Optiboot is configured to wait 8s for new programming activity before it boots user code.  

