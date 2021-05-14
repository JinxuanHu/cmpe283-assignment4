# cmpe283-assignment4
## Members:
Jinxuan Hu And Xuan Shi---
* Run the code in assignment3 with nested paging,    
* Run the code with shadow paging.
* Analyze the outputs of two modes.
* Create the document.


## Steps:
1.Environment setup: this assignment is based on Assignment3, so environment setup is the same as Assignment3.

2.Run the assignment3 code and boot a test VM using that code.

3.Remove 'kvm-intel' module in the outer 
4.Reload the kvm-intel module with the parameter ept=0 by using the following command:
`insmod  /lib/modules/5.12.0+/kernel/arch/x86/kvm/kvm-intel.ko ept=0`

## Output
1. with ept


2. without ept


## Questions
3.What did you learn from the count of exits? Was the count what you expected? If not, why not?   
A: As we can see from the output, the number of exits of 'without ept' is obviously larger than of 'with ept'. It's what I expected because in nested paging, it will only exit when an EPT violation occurs while in shadow paging, it could exit every time VM tries to excite CR0, CR3,CR4 or any paging exits.
   
4.What changed between the two runs (ept vs no-ept)?
A: The count of exits in NO-EPT Mode is larger than EPT Mode. 
