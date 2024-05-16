# PDU

네트워크의 어떠한 계층에서 계층으로 데이터가 전달될 때 한 덩어리의 단위

```bash
curl www.naver.com
```

![Untitled](7-images/Untitled.png)

- **Header, payload**로 구성되며, 계층마다 부르는 명칭이 다름
    - **Header**: 제어 관련 정보들
    - **Payload**: 데이터
- **계층별 명칭 및 역할**
    1. 애플리케이션 계층 (Application Layer) **메시지** 구조
        - 애플리케이션 계층 프로토콜(HTTP, FTP, SMTP 등)에 따라 패킷 구조가 다름
        - 일반적으로 애플리케이션 계층 패킷은 해당 프로토콜의 헤더와 페이로드(데이터)로 구성
    2. **전송 계층 (Transport Layer)**
        - TCP (Transmission Control Protocol) **세그먼트** 구조
            - Source Port (2 bytes) | Destination Port (2 bytes) | Sequence Number (4 bytes) | Acknowledgment Number (4 bytes) | Header Length (4 bits) | Reserved (3 bits) | Flags (9 bits) | Window Size (2 bytes) | Checksum (2 bytes) | Urgent Pointer (2 bytes) | Options (variable) | Data (variable)
        - UDP (User Datagram Protocol) **데이터그램** 구조
            - Source Port (2 bytes) | Destination Port (2 bytes) | Length (2 bytes) | Checksum (2 bytes) | Data (variable)
    3. **인터넷 계층 (Internet Layer)**
        - IP (Internet Protocol) **패킷** 구조
            - Version (4 bits) | IHL (4 bits) | DSCP (6 bits) | ECN (2 bits) | Total Length (2 bytes) | Identification (2 bytes) | Flags (3 bits) | Fragment Offset (13 bits) | Time to Live (1 byte) | Protocol (1 byte) | Header Checksum (2 bytes) | Source IP Address (4 bytes) | Destination IP Address (4 bytes) | Options (variable) | Data (variable)
    4. **데이터 링크 계층 (Data Link Layer)**
        - 이더넷 **프레임** 구조
            - Preamble (8 bytes) | Destination MAC Address (6 bytes) | Source MAC Address (6 bytes) | EtherType/Length (2 bytes) | VLAN Tag (optional, 4 bytes) | Payload (variable, 46-1500 bytes) | Frame Check Sequence (4 bytes)