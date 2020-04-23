<a name="crit-networking-step1"></a>
### <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>필수 사항: 네트워크에서 Microsoft 365 Enterprise 사용 준비 완료

- 사무실에 Office 365, Microsoft Intune, Windows 10 Enterprise 설치 및 업데이트를 포함하여 Microsoft 365 트래픽에 적합한 인터넷 대역폭이 있습니다.
- 전체 네트워크가 [Microsoft 365 참조 아키텍처](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)에 매핑됩니다.
- 네트워크 변경 사항이 시험 및 테스트되었으며 트래픽 대기 시간 요구 사항을 충족합니다.

필요한 경우 [1단계](../networking-provide-bandwidth-cloud-services.md)를 통해 이 요구 사항을 충족할 수 있습니다.

<a name="crit-networking-step2"></a>
### <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>필수 사항: 지사에 로컬 인터넷 연결 및 이름 확인 구성

해당 DNS 서버가 인터넷상의 위치를 식별하는 로컬 공용 IP 주소를 사용하도록 각 지사에 로컬 ISP를 통한 인터넷 액세스를 구성해야 합니다. 이렇게 하면 Microsoft 365 클라우드 서비스에 액세스하는 사용자에 대해 최상의 성능이 보장됩니다.

각 지사에 로컬 ISP를 사용하지 않으면 네트워크 트래픽이 조직의 백본 또는 원격 프런트 엔드 서버에서 제공하는 데이터 요청을 통과해야 하기 때문에 성능이 저하될 수 있습니다.

#### <a name="how-to-test"></a>테스트하는 방법
해당 사무실의 장치에서 도구 또는 웹 사이트를 사용하여 프록시 서버가 사용 중인 공용 IP 주소를 확인합니다. 예를 들어 [내 IP 주소](https://www.whatismypublicip.com/) 웹 페이지를 사용합니다. ISP에 의해 할당된 공용 IP 주소는 지리적으로 로컬이어야 하며, 본사의 공용 IP 주소 범위 또는 클라우드 기반 네트워크 보안 공급업체에서 제공되는 것이 아니어야 합니다.

필요한 경우 [2단계](../networking-dns-resolution-same-location.md)를 통해 이 요구 사항을 충족할 수 있습니다.

<a name="crit-networking-step3"></a>
### <a name="optional-unnecessary-network-hairpins-are-removed"></a>선택 사항: 불필요한 네트워크 헤어핀 제거

네트워크 헤어핀을 검사하고 모든 사무실의 성능에 미치는 영향을 확인했습니다. 가능한 경우 네트워크 헤어핀을 제거하거나 타사 네트워크 또는 보안 공급자와 함께 네트워크에 대한 최적 Microsoft 365 피어링을 구현했습니다.

필요한 경우 [3단계](../networking-avoid-network-hairpins.md)를 통해 이 옵션을 충족할 수 있습니다.


<a name="crit-networking-step4"></a>
### <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>선택 사항: 인터넷 브라우저 및 에지 장치에 대해 트래픽 바이패스 구성

Microsoft 365 DNS 도메인 이름으로의 트래픽이 프록시 서버를 무시하도록 온-프레미스 인터넷 브라우저로 최신 PAC 파일을 배포했습니다.

트래픽 바이패스를 사용하거나 Microsoft 365 끝점의 최적화 및 허용 범주로의 트래픽을 최소로 처리하도록 네트워크 경계 장치(예: 방화벽, SSL 중단 및 조사, 패킷 검사 장치)를 구성했습니다.


#### <a name="how-to-test"></a>테스트 방법

네트워크 경계 장치에서 로깅 도구를 사용하여 Microsoft 365 대상에 대해 검사, 암호 해독 또는 기타 방해 작업이 수행되지 않는지 확인합니다.

필요한 경우 [4단계](../networking-configure-proxies-firewalls.md)를 통해 이 옵션을 충족할 수 있습니다.


<a name="crit-networking-step5"></a>
### <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a>선택: 최적 성능을 위해 클라이언트 및 Office 365 응용 프로그램 구성

Exchange Online, 비즈니스용 Skype Online, SharePoint Online 및 Project Online 서비스에 대해 클라이언트 장치에서 TCP(전송 제어 프로토콜) 설정을 최적화해야 합니다.

필요한 경우 [5단계](../networking-optimize-tcp-performance.md)를 통해 이 옵션을 충족할 수 있습니다.
