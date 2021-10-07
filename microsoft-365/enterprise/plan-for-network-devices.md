---
title: Office 365 서비스에 연결되는 네트워크 장치 계획
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: '요약: 네트워크에 연결하는 데 사용되는 네트워크 용량, WAN 가속기 및 부하 분산 장치에 대한 고려 사항을 Office 365.'
ms.openlocfilehash: 38df9a64610c4b4d44014a142bf7d255aa0a0f46
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166781"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Office 365 서비스에 연결되는 네트워크 장치 계획

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*
  
일부 네트워크 하드웨어는 지원되는 동시 세션 수에 제한이 있을 수 있습니다. 사용자가 2,000명 이상인 조직의 경우 네트워크 장치를 모니터링하여 추가 서비스 트래픽을 처리할 Office 365 것이 좋습니다. SNMP(Simple Network Management Protocol) 모니터링 소프트웨어를 사용하면 이 작업을 쉽게 할 수 있습니다.

이 문서는 에 대한 네트워크 계획 및 성능 [조정의 Office 365.](./network-planning-and-performance.md)

또한 클라이언트 응용 프로그램에 대한 Office 365 연결에 영향을 주는 인터넷 프록시 설정도 있습니다. 또한 Microsoft 클라우드 서비스 URL 및 응용 프로그램에 대한 연결을 허용하도록 네트워크 프록시 장치를 구성해야 합니다. 조직마다 다릅니다. Microsoft에서 이 프로세스를 관리하는 방법과 프로비전하는 대역폭의 양에 대한 아이디어를 얻었다면 사례 [연구 를 읽어 읽습니다.](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)
  
다음 비즈니스용 Skype 도움말 문서에는 설정에 대한 자세한 비즈니스용 Skype 있습니다.
  
- [관리자를 비즈니스용 Skype 온라인 로그인 오류 문제 해결](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [프레미스 방화벽이 연결을 차단하기 때문에 비즈니스용 Skype 기능에 연결할 수 없는 경우 또는 특정 기능이 작동하지 않습니다.](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> 이러한 설정 중 상당수는 특정 비즈니스용 Skype, 네트워크 구성에 대한 일반적인 지침은 모든 Office 365 유용합니다.
  
## <a name="determining-network-capacity"></a>네트워크 용량 결정

연결에 있는 모든 네트워크 장치에는 용량 제한이 있습니다. 이러한 장치에는 클라이언트 및 서버 네트워크 어댑터, 라우터, 스위치 및 상호 연결된 허브가 포함됩니다. 적절한 네트워크 용량은 어떤 네트워크 용량도 포화 상태일 수 없음을 의미합니다. 네트워크 작업 모니터링은 모든 네트워크 장치의 실제 부하가 최대 용량보다 작아지게 하는 데 필수적입니다. 네트워크 용량은 프록시 장치 성능에 영향을 미치게 됩니다.
  
대부분의 경우 인터넷 연결 대역폭은 트래픽 양에 대한 제한을 설정합니다. 트래픽이 많은 시간에 성능이 약한 것은 인터넷 링크를 과도하게 사용하게 하여 발생할 수 있습니다. 이 상황은 느린 WAN(Wide Area Network) 링크를 통해 지점의 본사에 있는 프록시 장치에 지점 프록시 서버 컴퓨터가 연결된 지점 시나리오에도 적용됩니다.
  
네트워크 용량을 테스트하기 위해 프록시 네트워크 인터페이스에서 네트워크 활동을 모니터링합니다. 모든 네트워크 인터페이스의 최대 대역폭의 75%를 초과하는 경우 네트워크 인프라의 대역폭을 늘리는 것이 부적절한 경우를 고려합니다. 또는 HTTP 압축과 같은 고급 기능을 사용할 수 있습니다.
  
## <a name="wan-accelerators"></a>WAN 가속기

조직에서 WAN(Wide Area Network) 가속 프록시 어플라이언스를 사용하는 경우 WAN 서비스에 액세스할 때 Office 365 있습니다. 네트워크 장치 또는 장치를 최적화하여 사용자가 네트워크에 액세스할 때 일관된 환경을 Office 365. 예를 들어 Office 365 서비스에서 일부 Office 365 및 TCP 헤더를 암호화합니다. 디바이스에서 이러한 종류의 트래픽을 처리하지 않을 수 있습니다.
  
WAN 최적화 컨트롤러 또는 [트래픽/검사](https://support.microsoft.com/kb/2690045)장치와 함께 WAN 최적화 컨트롤러 사용에 대한 지원 Office 365.
  
## <a name="hardware-and-software-load-balancing-devices"></a>하드웨어 및 소프트웨어 부하 분산 장치

조직에서는 HLB(하드웨어 부하 분산 장치) 또는 NLB(네트워크 부하 분산) 솔루션을 사용하여 AD FS(Active Directory Federation Services) 서버 및/또는 하이브리드 서버로 요청을 Exchange 합니다. 부하 분산 장치는 사내 서버에 대한 네트워크 트래픽을 제어합니다. 이러한 서버는 Single Sign-On 및 하이브리드 배포의 가용성을 보장하는 데 Exchange 중요합니다.
  
Windows Server에 기본 제공되는 소프트웨어 기반 NLB 솔루션을 제공합니다. Office 365 솔루션을 지원하여 부하 분산을 실현할 수 있습니다.
  
## <a name="firewalls-and-proxies"></a>방화벽 및 Proxies

Office 365 연결할 방화벽 및 Office 365 구성에 대한 자세한 내용은 [Managing Office 365 endpoints,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) [Assessing Office 365 network connectivity](assessing-network-connectivity.md)및 Office 365 [endpoints FAQ를](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) 참조하여 장치 및 회로 선택에 대한 자세한 내용을 참조합니다.
  
## <a name="see-also"></a>참고 항목

[Office 365 설치 가이드](setup-guides-for-microsoft-365.md)

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)