# Reliable Transport Protocols

This project implements reliable transport protocols in C++ to simulate data transmission in a network. 
The protocols include **Alternating Bit Protocol (ABT)**, **Go-Back-N (GBN)**, and **Selective Repeat (SR)**, 
each tested under various conditions to evaluate their performance.
Through this class project, I dived deeper into the details of each protocol, and gained a more practical understanding of the principles reliable
data transfer

## Overview
The implementation simulates packet sending and receiving while considering loss and corruption in a network. Key features include:
- **Packet creation and acknowledgment**
- **Checksum calculation**
- **Sequence number management**
- **Timeout handling**

Protocols were tested using predefined experiments with varying packet loss and corruption probabilities.

## Protocol Descriptions
1. **Alternating Bit Protocol (ABT)**: 
   - A stop-and-wait protocol sending one packet at a time.
   - Simplistic but inefficient in high-loss scenarios.

2. **Go-Back-N (GBN)**:
   - Utilizes a single timer for unacknowledged packets.
   - Retransmits all unacknowledged packets upon timeout.

3. **Selective Repeat (SR)**:
   - Employs logical timers for each packet in the sender's window.
   - Retransmits only lost packets, offering better throughput.

## Results Summary
- **Throughput Analysis**:
  - ABT suffers from consistently low throughput.
  - GBN performs well in low-loss settings but struggles with higher loss rates.
  - SR demonstrates high efficiency, especially with larger window sizes.
- **Window Size Impact**:
  - GBN shows minimal improvement with larger window sizes.
  - SR benefits significantly from increased window sizes, showcasing its scalability.

## Challenges
- Debugging timer logic for GBN and SR.
- Addressing terminal hangs in SR due to excessive packet drops.
- Understanding and implementing buffer size adjustments.

## Testing
The implementation passed all tests:
- `./sanity_tests -h`
- `./basic_tests -h`
- `./advanced_tests -h`
- `./run_experiments -h`

## Dependencies
- C++ Compiler
- Course textbook: *Computer Networking: A Top-Down Approach* by Kurose and Ross

## References
- [RFC 793](https://www.ietf.org/rfc/rfc793.txt) - TCP Implementation
- Discussions on JuliaLang and other online programming communities

## How to Run
1. Clone the repository.
2. Compile the C++ code.
3. Execute the test scripts provided to simulate experiments.

## Author
- **Germain Mucyo**
- Email: mucyo.g@northeastern.edu
