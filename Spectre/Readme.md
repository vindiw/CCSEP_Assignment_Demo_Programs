# Mitigation
### Intel lfence style mitigation

##### The following CFLAG was added to Makefile

#### CFLAGS=-DINTEL_MITIGATION

# Compiling

```
make
```
# Following was Tested on Intel Core i5-8265U running Microsoft WSL2 - Ubuntu 20.04.4 LTS

# Executing
```
./spectre.out
```
## Example Output 
```
Using a cache hit threshold of 80.
Build: RDTSCP_SUPPORTED MFENCE_SUPPORTED CLFLUSH_SUPPORTED INTEL_MITIGATION_ENABLED LINUX_KERNEL_MITIGATION_DISABLED
Reading 16 bytes:
Reading at malicious_x = 0xffffffffffffdfe8... Unclear: 0x01=’?’ score=763 (second best: 0x00=’?’ score=464)
Reading at malicious_x = 0xffffffffffffdfe9... Unclear: 0x01=’?’ score=724 (second best: 0x00=’?’ score=513)
Reading at malicious_x = 0xffffffffffffdfea... Unclear: 0x01=’?’ score=752 (second best: 0x00=’?’ score=486)
Reading at malicious_x = 0xffffffffffffdfeb... Unclear: 0x01=’?’ score=743 (second best: 0x00=’?’ score=457)
Reading at malicious_x = 0xffffffffffffdfec... Unclear: 0x01=’?’ score=784 (second best: 0x00=’?’ score=581)
Reading at malicious_x = 0xffffffffffffdfed... Success: 0x01=’?’ score=155 (second best: 0x00=’?’ score=72)
Reading at malicious_x = 0xffffffffffffdfee... Unclear: 0x01=’?’ score=776 (second best: 0x00=’?’ score=460)
Reading at malicious_x = 0xffffffffffffdfef... Unclear: 0x01=’?’ score=742 (second best: 0x00=’?’ score=517)
Reading at malicious_x = 0xffffffffffffdff0... Success: 0x01=’?’ score=23 (second best: 0x00=’?’ score=10)
Reading at malicious_x = 0xffffffffffffdff1... Unclear: 0x01=’?’ score=796 (second best: 0x00=’?’ score=457)
Reading at malicious_x = 0xffffffffffffdff2... Unclear: 0x01=’?’ score=761 (second best: 0x00=’?’ score=503)
Reading at malicious_x = 0xffffffffffffdff3... Unclear: 0x01=’?’ score=758 (second best: 0x00=’?’ score=456)
Reading at malicious_x = 0xffffffffffffdff4... Unclear: 0x01=’?’ score=761 (second best: 0x00=’?’ score=481)
Reading at malicious_x = 0xffffffffffffdff5... Unclear: 0x01=’?’ score=769 (second best: 0x00=’?’ score=545)
Reading at malicious_x = 0xffffffffffffdff6... Unclear: 0x01=’?’ score=770 (second best: 0x00=’?’ score=528)
Reading at malicious_x = 0xffffffffffffdff7... Unclear: 0x01=’?’ score=717 (second best: 0x00=’?’ score=501)
```
