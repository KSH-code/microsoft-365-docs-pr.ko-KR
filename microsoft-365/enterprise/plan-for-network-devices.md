---
title: Office 365 서비스에 연결되는 네트워크 장치 계획
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: '요약: Office 365에 연결하는 데 사용되는 네트워크 용량, WAN 가속기 및 부하 분산 장치에 대한 고려 사항을 제공합니다.'
ms.openlocfilehash: a4ea75eb294d74004125be4d258dbe86d7d89810
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692539"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Office 365 서비스에 연결되는 네트워크 장치 계획

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*
  
일부 네트워크 하드웨어에는 지원되는 동시 세션 수에 제한이 있을 수 있습니다. 사용자가 2,000명 이상인 조직의 경우 네트워크 장치를 모니터링하여 추가 Office 365 서비스 트래픽을 처리할 수 있도록 하는 것이 좋습니다. SNMP(Simple Network Management Protocol) 모니터링 소프트웨어를 사용하면 이 작업을 쉽게 할 수 있습니다.

이 문서는 [Office 365에](https://aka.ms/tune)대한 네트워크 계획 및 성능 조정의 일부입니다.

또한 클라이언트 응용 프로그램의 Office 365 서비스에 대한 연결에 영향을 주는 프레미스 아웃소드 인터넷 프록시 설정도 영향을 받을 수 있습니다. 또한 Microsoft 클라우드 서비스 URL 및 응용 프로그램에 대한 연결을 허용하도록 네트워크 프록시 장치를 구성해야 합니다. 조직마다 다릅니다. Microsoft에서 이 프로세스를 관리하는 방법과 프로비전하는 대역폭의 양에 대한 아이디어를 얻습니다. 사례 [연구를 읽어 읽습니다.](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)
  
다음 비즈니스용 Skype 도움말 문서에는 비즈니스용 Skype 설정에 대한 자세한 정보가 있습니다.
  
- [관리자를 위한 비즈니스용 Skype Online 로그인 오류 문제 해결](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [비즈니스용 Skype에 연결할 수 없는 경우 또는 특정 기능이 작동하지 않는 경우,프레미스 방화벽에서 연결을 차단하기 때문에](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> 이러한 설정 중 상당수는 비즈니스용 Skype 관련 설정이지만 네트워크 구성에 대한 일반적인 지침은 모든 Office 365 서비스에 유용합니다.
  
## <a name="determining-network-capacity"></a>네트워크 용량 결정

연결에 있는 모든 네트워크 장치에는 용량 제한이 있습니다. 이러한 장치에는 상호 연결된 클라이언트 및 서버 네트워크 어댑터, 라우터, 스위치 및 허브가 포함됩니다. 적절한 네트워크 용량은 그 어느 것도 포화 상태가 없음을 의미합니다. 네트워크 작업 모니터링은 모든 네트워크 장치의 실제 부하가 최대 용량 미만이 되도록 하는 데 필수적입니다. 네트워크 용량은 프록시 장치 성능에 영향을 미치게 됩니다.
  
대부분의 경우 인터넷 연결 대역폭은 트래픽 양에 대한 제한을 설정합니다. 트래픽이 많은 시간 동안 성능이 약한 원인은 인터넷 링크를 과도하게 사용하기 때문에 발생할 수 있습니다. 이 상황은 저속 WAN(Wide Area Network) 링크를 통해 지점의 본사에 있는 프록시 장치에 지점 프록시 서버 컴퓨터가 연결된 지점 시나리오에도 적용됩니다.
  
네트워크 용량을 테스트하기 위해 프록시 네트워크 인터페이스에서 네트워크 활동을 모니터링합니다. 네트워크 인터페이스의 최대 대역폭의 75%를 초과하는 경우 네트워크 인프라의 대역폭을 늘리는 것이 부적절한 경우를 고려합니다. 또는 HTTP 압축과 같은 고급 기능을 사용할 수 있습니다.
  
## <a name="wan-accelerators"></a>WAN 가속기

조직에서 WAN(Wide Area Network) 가속 프록시 어플라이언스를 사용하는 경우 Office 365 서비스에 액세스할 때 문제가 발생할 수 있습니다. 사용자가 Office 365에 액세스할 때 일관된 환경을 제공하도록 네트워크 장치 또는 장치를 최적화해야 할 수 있습니다. 예를 들어 Office 365 서비스는 일부 Office 365 콘텐츠와 TCP 헤더를 암호화합니다. 디바이스가 이러한 종류의 트래픽을 처리하지 못할 수 있습니다.
  
[Office 365에서 WAN](https://support.microsoft.com/kb/2690045)최적화 컨트롤러 또는 트래픽/검사 장치 사용에 대한 지원 설명을 읽어 읽습니다.
  
## <a name="hardware-and-software-load-balancing-devices"></a>하드웨어 및 소프트웨어 부하 분산 장치

조직에서는 HLB(하드웨어 부하 분산) 또는 NLB(네트워크 부하 분산) 솔루션을 사용하여 AD FS(Active Directory Federation Services) 서버 및/또는 Exchange 하이브리드 서버로 요청을 배포해야 합니다. 부하 분산 장치는 네트워크에 대한 트래픽을 제어합니다. 이러한 서버는 Single Sign-On 및 Exchange 하이브리드 배포의 가용성을 보장하는 데 중요합니다.
  
Windows Server에 기본 제공되는 소프트웨어 기반 NLB 솔루션을 제공합니다. Office 365는 부하 분산을 위해 이 솔루션을 지원합니다.
  
## <a name="firewalls-and-proxies"></a>방화벽 및 Proxies

Office 365에 연결하기 위한 방화벽 및 팩스 구성에 대한 자세한 내용은 Office 365 끝점 관리, [Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)네트워크 연결 평가 및 Office [365](assessing-network-connectivity.md)끝점 [FAQ를](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) 읽어 장치 및 회로 선택에 대한 자세한 내용을 확인합니다.
  
## <a name="see-also"></a>참고 항목

[Office 365 서비스에 대한 설치 가이드](setup-guides-for-microsoft-365.md)

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)
