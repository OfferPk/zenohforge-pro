# ZenohForge Pro Technical Architecture & Specification

## 1\. Eclipse Zenoh Protocol Overview

Eclipse Zenoh is a pub/sub/query protocol designed for robotics, edge computing, and distributed embedded devices. Operating under a minimal wire footprint, Zenoh combines traditional publication/subscription streaming with location-transparent distributed storage queries and remote procedure calls (RPC).

### Key Technical Pillars:

1. **Hierarchical Key Expressions**: Zenoh replaces flat topic strings with URL-like path expressions (e.g., `robot/arm/joint_states`). These support single-level (`*`) and multi-level (`**`) wildcards for flexible dynamic routing.  
2. **Variable-Length 7-Bit ZInt Encoding**: Framing headers minimize serialized byte length using compact continuation bit encodings (LEB128).  
3. **Dynamic Resource ID Declarations**: Through the `DECLARE` message, peers map lengthy text key expressions to small integer tokens, reducing per-packet header overhead to under 6-10 bytes.  
4. **Queryables & Distributed Storage**: Distributed nodes advertise capability as Queryables, responding to targeted or network-wide `GET` requests with asynchronous `REPLY` messages.  
5. **ROS 2 Integration (rmw\_zenoh)**: Serves as the high-throughput, low-latency alternative to DDS for multi-robot fleets and bandwidth-constrained wireless links.