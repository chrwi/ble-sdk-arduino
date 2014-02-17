Release notes 0.8.0:

##Known issues:

1. Assert functionality has been removed and should be put back to the SDK.
Currently the asserts have been replaced with while(1)

2. Platforms specific code to be placed in a #define to improve portability
EIMSK. pgmspace etc.

3. The BLE module when using interrupts may have issues that may stop the libray from working when the FIFO/Queue becomes full.
When using interrupts ensure that the queue size is at least 4.
Specified in hal_aci_tl.h
#define ACI_QUEUE_SIZE  4
The BLE module does not have any known issues when polling.

4. The FIFO/Queue uses the "one slot" free method to detect empty and full conditions.
This wastes one extra element in the queue.
The algorithm can be optimized to reduce the RAM usage.

5. Bonding info is stored on non-volatile store on Arduino on Timing Event and Timing Event may not always arrive.
This issue is applicable for all projects that use pairing.

6. Documentation for using the Nordic adapter shield for nRF8001 with the nRF8001 Development kit and the Bluetooth low energy SDK for Arduino is incomplete.

7. Documentation for the Bluetooth low energy SDK for Arduino is still in progress.