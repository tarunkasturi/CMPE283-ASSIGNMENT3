# CMPE283-ASSIGNMENT3: INSTRUMENTATION VIA HYPERCALL

TEAM MEMBERS:
TARUN PRADEEP KASTURI (015349685)
HARSHIT BHORASKAR (

Contribution:
Tarun Kasturi:
Made changes in vmx.c to know the exit types by exit reason.
Made changes in cpuid.c to develop new LEAF node.
Developed a user program to print count for all exit reasons.

Harshit Bhoraskar:
Get to know about exit types which were not defined by SDM and not initialted in KVM and made changes accordingly in the cpuid.c to control exit types.
Installation of cpuid package and about its usage.
Developed a user program to print count fora specific exit reason.


Environment Setup:
We followed the same setup followed by the assignment 2

For the outer VM we have done the following:
1. Removed the kvm anf kvm intel modules

   $ sudo rmmod kvm..intel
   $ sudo rmmod kvm
  
  
2. Compile the updated kernal module

   $ sudo make -j 8 modules M=arch/x86/kvm
   
   
3. Install the modules

   $ sudo insmod arch/x86/kvm/kvm.ko
   $ sudo insmod arch/x86/kvm/kvm-intel.ko
   
4. In inner Vm install the cpuid package.

5. In terminal to test each leaf node run the following command

  $ cpuid -I 0x4ffffffd -s exit..number 
  
6. To view output run the following command "dmesg".  
   

