---
title: 초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 07/08/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 1492cb94-bd62-43e6-b8d0-2a61ed88ebae
ms.collection:
- M365-security-compliance
- Ent_O365
- SPO_Content
description: 초기에 새로운 문제를 감지하는 데 도움이 될 수 있도록 클라이언트 컴퓨터 연결의 기록을 검사하는 방법을 알아보는 방법을 배워야 합니다.
ms.openlocfilehash: 3a294bd00f1fdfd6fb8d04130193658c4eeea2d4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209600"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정

연결의 대략적인 기준을 설정할 수 있도록 Office 365 비즈니스 간의 연결 성능을 확인할 수 있는 몇 가지 간단한 방법이 있습니다. 클라이언트 컴퓨터 연결의 성능 기록을 파악하면 새로운 문제를 조기 검색하고, 식별하고, 예측하는 데 도움이 될 수 있습니다.
  
성능 문제를 해결하지 않는 경우 이 문서는 일반적인 질문을 고려하는 데 도움이 하도록 디자인된 것입니다. 보고 있는 문제를 어떻게 알 수 있나요? 서비스 인시던트가 아닌 성능 Office 365 있나요? 장기적인 양호한 성능을 계획할 수 있는 방법 성능을 어떻게 유지할 수 있나요? 팀 또는 클라이언트가 클라이언트를 사용하는 동안 성능이 Office 365 이러한 질문이 궁금한 경우 계속 읽어 봐야 합니다.
  
> [!IMPORTANT]
> **현재 클라이언트와 클라이언트 간의 성능 Office 365 문제가 있나요?** 에 대한 성능 문제 해결 계획에 [설명된 단계를 Office 365.](performance-troubleshooting-plan.md) 
    
## <a name="something-you-should-know-about-office-365-performance"></a>성능에 대해 알아야 할 Office 365 있습니다.

Office 365 및 실제 사용자에 의해 모니터링되는 대용량 전용 Microsoft 네트워크 내부에 있습니다. 클라우드를 유지 관리하는 Office 365 가능한 경우 성능 조정 및 간소화입니다. Office 365 클라우드의 클라이언트는 인터넷을 통해 연결해야 하기 때문에 여러 서비스에서 성능을 세부적으로 조정하기 위한 노력이 Office 365 있습니다.

성능 향상은 클라우드에서 절대 중지되지 않습니다. 따라서 클라우드를 건강하고 빠르게 유지하는 데는 경험하지 않습니다. 위치에서 다른 위치로 연결하는 성능 문제가 Office 365 지원 사례를 시작하거나 대기하지 않는 것이 좋습니다. 대신 '내부 내부'에서 문제 조사를 시작해야 합니다. 즉, 네트워크 내부에서 시작하여 네트워크 내부에서 Office 365. 지원 센터에서 사례를 열기 전에 데이터를 수집하고 문제를 탐색하고 해결할 수 있는 조치를 취할 수 있습니다.
  
> [!IMPORTANT]
> 용량 계획 및 제한에 Office 365. 이 정보는 성능 문제를 해결하려고 할 때 곡선을 앞서나가게 됩니다. 다음은 서비스 설명 및 Microsoft 365 [Office 365 링크입니다.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) 이 허브는 중앙 허브로, 여기에서 Office 365 서비스 설명으로 연결되는 링크가 있습니다. 즉, SharePoint Online에 대한 표준 제한을 보려면 SharePoint [Online](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description) 서비스 설명을 클릭하고 해당 SharePoint 온라인 제한 섹션을 [찾습니다.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
  
성능은 미끄러지기 확장에 대한 이해를 통해 문제 해결에 들어가야 합니다. 이상화된 가치를 달성하고 영구적으로 유지 관리하는 것이 아니라. 많은 수의 사용자를 추가하거나 대규모 데이터 마이그레이션을 수행하는 등 대역폭이 높은 작업을  수행하는 경우도 있으므로 성능에 미치는 영향을 계획하십시오. 성능 목표에 대한 대략적인 개념이 있지만 성능에는 많은 변수가 작용하기 때문에 성능이 다릅니다.
  
성능 문제 해결은 특정 목표를 달성하고 이러한 숫자를 무기한 유지 관리하는 것이 아니라 모든 변수를 통해 기존 활동을 개선하는 것입니다. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>성능 문제가 어떻게 보이나요?

먼저 발생하는 문제가 서비스 인시던트가 아닌 성능 문제인지 확인해야 합니다. 성능 문제는 2016년 8월의 서비스 인시던트와 Office 365. 이들을 분리하는 방법에는 다음이 있습니다.
  
서비스 인시던트는 서비스 Office 365 문제가 있는 경우 발생됩니다. 현재 상태 아래에 빨강 또는 노란색 아이콘이 **표시될** Microsoft 365 관리 센터. 클라이언트 컴퓨터에 연결되는 클라이언트 컴퓨터의 성능은 Office 365 있습니다. 예를 들어 현재 상태 보고서에 빨간색  아이콘이 보고되고 Exchange 옆에 조사 중이 표시될 경우 조직의 사용자로부터 전화를 받을 수도 있습니다. 이 경우 조직의 사용자로부터 클라이언트 사서함이 느리게 Exchange Online 있습니다. 이 경우 서비스 문제로 Exchange Online 성능에 문제가 있는 것으로 가정하는 것이 합리적입니다.
  
![서비스 Office 365 표시하는 작업을 제외한 모든 워크로드가 녹색으로 Exchange 상태 대시보드입니다.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
이제 Office 365 관리자인 사용자는 현재 상태와 세부  정보 및 기록 보기를 확인하여 시스템 유지 관리에 대한 최신 정보를 유지 관리해야 합니다. 현재 **상태 대시보드는** 서비스의 변경 내용 및 문제에 대해 업데이트하기 위해 만들어졌다. 상태 기록, 관리자에게 기록된 메모 및 설명은 사용자가 측정하고 지속적인 업무에 대해 계속 게시할 수 있도록 도움을 줄 수 있습니다.
  
![Office 365 서비스가 복원된 이유와 Exchange Online 설명하는 Exchange Online 상태 대시보드의 그림입니다.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
인시던트로 인해 성능이 저하될 수 있는 경우에도 성능 문제는 서비스 인시던트가 아닙니다. 성능 문제는 다음과 같습니다.
  
- 성능 문제는 관리 센터에서 서비스에 대해 보고하는 상태와 **상관없이** 발생합니다.
    
-  흐름에 사용된 동작은 완료하는 데 시간이 오래 걸리거나 완료되지 않습니다.
    
- 문제도 복제할 수 있습니다. 또는 올바른 일련의 단계를 수행하면 문제가 발생하게 될지 알 수 있습니다.
    
-  문제가 간헐적으로 발생하면 패턴이 있을 수 있습니다. 예를 들어 오전 10시까지 항상 액세스할 수 없는 사용자의 전화를 Office 365. 통화는 정오를 전제로 종료됩니다.
    
이 목록은 익숙한 것일 수 있습니다. 너무 익숙할 수 있습니다. 성능 문제가 발생하면 질문이 "다음에 어떻게 해야 나요?"가 됩니다. 이 문서의 나머지부분은 정확히 이를 확인하는 데 도움이 됩니다.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>성능 문제를 정의하고 테스트하는 방법

성능 문제는 시간이 지날 때 종종 발생하기 때문에 실제 문제를 정의하기 어려울 수 있습니다. 문제 컨텍스트를 잘 알 수 있는 좋은 문제 설명을 만든 다음 반복 가능한 테스트 단계를 실행해야 합니다. 다음은 충분한 정보를 제공하지 않는 문제 설명의 몇 가지 예입니다.
  
- 받은 편지함에서 내 일정으로 전환하는 중에는 눈에 띄지 않았던 것이지만 이제는 커피를 마신 것입니다. 사용할 수 있는 것 같은 역할을 할 수 있나요?
    
- 내 파일을 온라인 SharePoint 업로드하는 데는 이행이 든 것입니다. 오후에는 느리지만 그 외의 경우 속도가 빠릅니다. 빠를 수 없는가요?
    
위의 문제 진술에 의해 몇 가지 큰 문제가 발생했습니다. 특히 너무 많은 모호한 처리가 있습니다. 예를 들어:
  
- 노트북에서 받은 편지함과 일정을 전환하는 방식은 불분명합니다.
    
- 사용자가 "빠를 수 없습니다."라고 말하면 "빠르면"이란?
    
- How long is "forever"? 몇 초입니까? 또는 몇 분이 있나요? 또는 사용자가 점심을 드시고 다시 돌아와서 10분 후에 작업을 완료할 수 있나요?
    
관리자와 문제 해결사는 이러한 일반적인  설명에서 문제의 세부 정보를 인식할 수 없습니다. 예를 들어 문제가 언제 발생하기 시작했다는 것을 알지 못합니다. 문제 해결사는 사용자가 집에서 작업하는지 알 수 없는데 홈 네트워크에 있는 동안에는 저속 전환만 볼 수 있습니다. 또는 사용자가 로컬 클라이언트에서 다른 RAM을 많이 사용하는 응용 프로그램을 실행합니다. 관리자는 사용자가 이전 운영 체제를 실행 중이거나 최신 업데이트를 실행하지 않은 경우를 알 수 있습니다.
  
사용자가 성능 문제를 보고하면 수집할 정보가 많이 있습니다. 정보를 받고 기록하는 것을 문제의 곱하기라고 합니다. 다음은 성능 문제에 대한 정보를 수집하는 데 사용할 수 있는 기본 너비 목록입니다. 이 목록은 전체 목록이 아니라 시작할 수 있는 장소입니다.
  
- 어떤 날짜에 문제가 발생하고 하루 중 어떤 시간이 발생했습니까?
    
- 사용 중이던 클라이언트 컴퓨터의 종류와 비즈니스 네트워크(VPN, 유선, 무선)에 어떻게 연결하나요?
    
- 원격으로 작업 중이거나 사무실에 있나요?
    
- 다른 컴퓨터에서 동일한 작업을 시도하고 동일한 동작을 표시했습니까?
    
- 문제를 해결하고 있는 작업을 작성할 수 있도록 단계를 진행합니다.
    
- 성능은 몇 초 또는 몇 분 정도 느리나요?
    
- 전 세계 어디에 있나요?
    
이러한 질문 중 일부는 다른 질문보다 더 명확합니다. 대부분의 모든 사람은 문제 해결사에서 문제를 재현하는 정확한 단계가 필요하다는 것을 이해합니다. 결국 다른 문제를 기록할 수 있는 방법과 문제가 해결된 경우 어떻게 테스트할 수 있나요? "문제가 어떤 날짜와 시간이 표시 했나요?", "현재 위치는 어디인가요?"처럼 명확하지 않은 정보를 함께 사용할 수 있습니다. 사용자가 근무한 시간에 따라 몇 시간의 시간 차이로 회사 네트워크의 일부에서 유지 관리가 이미 진행 중일 수 있습니다. 예를 들어 회사에 SharePoint Online 및 SharePoint Server 2013 인스턴스의 검색 인덱스를 쿼리할 수 있는 하이브리드 SharePoint Search와 같은 하이브리드 구현이 있는 경우, 업데이트가 사내 팜에서 진행될 수 있습니다. 회사가 모두 클라우드에 있는 경우 시스템 유지 관리에는 네트워크 하드웨어 추가 또는 제거, 회사 전체의 업데이트 롤아웃 또는 DNS 또는 기타 핵심 인프라 변경이 포함됩니다.
  
성능 문제를 해결할 때 범죄 현장과 약간 같은 경우 증거에서 결론을 도출하려면 정확하고 관찰적이 필요합니다. 이를 위해서는 증거를 수집하여 좋은 문제 설명을 얻을 수 있어야 합니다. 여기에는 컴퓨터의 컨텍스트, 사용자의 컨텍스트, 문제가 시작된 때 및 성능 문제를 노출한 정확한 단계가 포함되어야 합니다. 이 문제 설명은 메모에서 맨 위에 있는 페이지로 유지해야 합니다. 해결 방법을 수행한 후 문제 설명을 다시 확인하여 조치를 수행하여 문제를 해결한 것인지 테스트하고 증명하는 단계를 수행하게 됩니다. 이 설정은 작업의 완료 시를 아는 데 중요합니다.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>성능이 양호한 경우의 성능을 어떻게 볼 수 있나요?

문제가 없는 경우 아무도 알 수 없습니다. 누구도 숫자를 들이지 못합니다. 즉, 아무도 "Office 365에서 받은 편지함을 가져오는 데 몇 초 정도 걸릴까요?"라는 간단한 질문이나 "임원이 Lync Online 모임을 할 때 얼마나 오래 사용했나요?"라는 간단한 질문에 대답할 수 없습니다. 이는 많은 회사에서 흔히 볼 수 있는 시나리오입니다.
  
여기서 누락된 것은 성능 기준입니다.
  
기준은 성능에 대한 컨텍스트를 제공합니다. 회사의 요구에 따라 종종 기준을 세우는 것이 좋습니다. 대기업의 경우 Operations 팀이 이미 사내 환경에 대한 기준을 사용할 수 있습니다. 예를 들어 첫 번째 월요일에 모든 Exchange 서버를 패치하고 세 번째 월요일에 모든 SharePoint 서버를 패치하는 경우 작업 팀에는 패치 후 실행되는 작업 및 시나리오 목록이 표시되어 중요한 기능이 작동하고 있는 것을 증명할 수 있습니다. 예를 들어 받은 편지함을 열고 보내기/받기를 클릭한 다음 폴더가 업데이트되어 있는지 확인하거나SharePoint 사이트의 기본 페이지를 찾아 엔터프라이즈 검색 페이지로 이동한 다음 결과를 반환하는 검색을 수행하도록 할 수 있습니다.
  
응용 프로그램이 Office 365 경우 가장 기본적인 기준 중 일부는 네트워크 내부의 클라이언트 컴퓨터, 발신 지점 또는 네트워크를 떠나 네트워크로 나가는 지점까지의 시간을 밀리초로 측정할 수 Office 365. 다음은 조사하고 기록할 수 있는 몇 가지 유용한 기준입니다.
  
- 클라이언트 컴퓨터와 시작 지점 간의 장치(예: 프록시 서버)를 식별합니다.
    
  - 발생하는 성능 문제에 대한 컨텍스트(IP 주소, 장치 유형, et cetera)가 있도록 디바이스를 알아야 합니다.
    
  - 프록시 서버는 일반적인 전송 지점이기 때문에 웹 브라우저에서 사용할 프록시 서버(있는 경우)를 확인할 수 있습니다.
    
  - 네트워크를 검색하고 매핑할 수 있는 타사 도구가 있지만 장치를 아는 가장 안전한 방법은 네트워크 팀 구성원에게 요청하는 것입니다.
    
- ISP(인터넷 서비스 공급자)를 식별하고, 연락처 정보를 기록하고, 대역폭의 수를 묻습니다.
    
- 회사 내에서 클라이언트와 시작 지점 사이의 장치에 대한 리소스를 식별하거나 네트워킹 문제에 대해 논의할 긴급 연락처를 식별합니다.
    
다음은 도구를 사용하여 간단한 테스트를 통해 계산할 수 있는 몇 가지 기준입니다.
  
- 클라이언트 컴퓨터에서 시작 지점까지의 시간(밀리초)입니다.
    
- 시작 지점에서 Office 365 시간(밀리초)입니다.
    
- 검색할 때 서버의 URL을 Office 365 위치
    
- ISP의 DNS 확인 속도(밀리초), 패킷 도착 시 불일치(네트워크 지터), 업로드 및 다운로드 시간(밀리초)
    
이러한 단계를 수행하기에 익숙하지 않은 경우 이 문서에서 자세히 설명할 것입니다. 
  
## <a name="what-is-a-baseline"></a>기준이란?

문제가 있을 때의 영향을 알 수 있지만 기록 성능 데이터를 모르는 경우 악의적인 상황과 그 때에 대한 컨텍스트를 사용할 수 없습니다. 따라서 기본이 없는 경우 퍼즐을 해결하기 위한 키 단서( 퍼즐 상자의 그림)가 없습니다. 성능 문제 해결에서 비교 지점이 *필요합니다.* 간단한 성능 기준은 사용하기가 어렵습니다. 작업 팀에서는 이러한 작업을 일정에 따라 수행해야 할 수 있습니다. 예를 들어 연결의 모양은 다음과 같습니다. 
  
![클라이언트, 프록시 및 클라우드를 보여 Office 365 네트워크 그래픽입니다.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
즉, 네트워크 팀에 확인한 결과 프록시 서버를 통해 회사를 퇴사하고 해당 프록시는 클라이언트 컴퓨터가 클라우드로 보내는 모든 요청을 처리합니다. 이 경우 모든 중간 장치를 나열하는 간소화된 버전의 연결을 그려야 합니다. 이제 클라이언트, 나가는 지점(인터넷을 위해 네트워크를 떠날 위치) 및 클라우드와 클라우드 간의 성능을 테스트하는 데 사용할 수 있는 Office 365 삽입합니다.
  
![클라이언트, 프록시 및 클라우드가 있는 기본 네트워크와 PSPing, TraceTCP 및 네트워크 추적을 제안하는 도구가 있습니다.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
성능 데이터를 찾는 데  필요한 전문 지식이 있기 때문에 옵션이 **단순** 및 고급으로 나열됩니다. 네트워크 추적은 PsPing 및 TraceTCP와 같은 명령줄 도구를 실행하는 데 비해 시간이 많이 걸릴 수 있습니다. 이러한 두 명령줄 도구는 Office 365 의해 차단되는 ICMP 패킷을 사용하지 않는 것이고 클라이언트 컴퓨터 또는 프록시 서버(액세스 권한이 있는 경우)에서 퇴장하고 ICMP에 도착하는 데 걸리는 시간(밀리초)을 제공하기 때문에 Office 365. 한 컴퓨터에서 다른 컴퓨터로의 각 개별 홉은 시간 값으로 끝나며 이는 기준에 좋습니다. 중요한 점은 이러한 명령줄 도구를 사용하여 명령에 포트 번호를 추가할 수 있습니다. 이 기능은 Office 365 및 SSL 및 TLS(전송 계층 보안)에서 사용하는 포트인 Office 365 Secure Sockets Layer 통신하기 때문에 유용합니다. 그러나 다른 타사 도구는 상황에 대한 더 나은 솔루션일 수 있습니다. Microsoft는 이러한 도구를 모두 지원하지 않습니다. 따라서 어떤 이유로 PsPing 및 TraceTCP를 사용할 수 없는 경우 Netmon과 같은 도구를 사용하여 네트워크 추적으로 이동하세요. 
  
업무 시간 전에 기준을 다시 세우고, 과도하게 사용하는 동안에는 다시 한 번 시간을 사용할 수 있습니다. 즉, 다음과 같은 폴더 구조가 끝에 있을 수 있습니다.
  
![성능 데이터를 폴더로 구성하는 방법을 제시하는 그래픽](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
파일 이름 규칙도 선택해야 합니다. 다음은 몇 가지 예입니다.
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
다양한 방법으로 이 작업을 시작할 수 있지만 형식을 사용하는 **\<dateTime\>\<what's happening in the test\>** 것이 좋습니다. 이에 대해 부지런히 생각하면 나중에 문제를 해결하려고 할 때 많은 도움이 됩니다. 나중에 "2월 8일 두 번의 추적을 진행했습니다. 하나는 좋은 성능을 보여 주며 다른 하나는 좋지 않은 결과를 나타났기 때문에 비교할 수 있습니다."라고 말할 수 있습니다. 이 방법은 문제 해결에 매우 유용합니다. 
  
기록 기준을 유지할 수 있는 체계적인 방법이 필요합니다. 이 예제에서는 간단한 메서드로 세 개의 명령줄 출력이 생성되고 결과가 스크린샷으로 수집되지만 대신 네트워크 캡처 파일이 있을 수 있습니다. 가장 적합한 메서드를 사용합니다. 기록 기준을 저장하고 온라인 서비스의 동작이 변경되는 지점에서 참조하세요. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>파일럿 중에 성능 데이터를 수집하는 이유

기본 서비스를 파일럿하는 동안보다 기준을 세우는 것이 더 Office 365 없습니다. 사무실에 수천 명의 사용자가 있을 수도, 수만 명이나 다섯 명일 수도 있지만, 소수의 사용자라도 테스트를 수행하여 성능 변동을 측정할 수 있습니다. 대기업의 경우 수백 명의 사용자로 구성되는 대표 샘플을 Office 365 수 있습니다. 따라서 문제가 발생하기 전에 발생할 수 있는 위치를 알 수 있습니다.
  
모든 사용자가 동시에 서비스로 이동하고 파일럿이 없음을 의미하는 소규모 회사인 경우 성능이 좋지 않은 작업 문제를 해결해야 할 수 있는 사용자에게 데이터를 표시하기 위해 성능 측정값을 유지하십시오. 예를 들어 갑작스러운 일이 발생하면 중간 크기의 그래픽을 업로드하는 데 걸리는 시간 동안 빠르게 건물을 돌아다니는 것을 알 수 있습니다.
  
## <a name="how-to-collect-baselines"></a>기준을 수집하는 방법

모든 문제 해결 계획의 경우 최소한 다음을 식별해야 합니다.
  
- 사용 중이신 클라이언트 컴퓨터(컴퓨터 또는 장치 유형, IP 주소 및 문제를 유발한 작업)
    
- 클라이언트 컴퓨터가 전 세계에 있는 위치(예: 이 사용자가 네트워크에 VPN을 사용하는지, 원격으로 작업하는지 또는 회사 인트라넷에서 작업하는지 여부)
    
- 클라이언트 컴퓨터가 네트워크에서 사용하는 시작 지점(트래픽이 ISP 또는 인터넷을 위해 비즈니스를 떠나는 지점)
    
 네트워크 관리자에서 네트워크 레이아웃을 찾을 수 있습니다. 소규모 네트워크에 있는 경우 인터넷에 연결하는 장치를 살펴보고 레이아웃에 대한 질문이 있는 경우 ISP에 전화를 걸 수 있습니다. 참조에 대한 최종 레이아웃의 그래픽을 생성합니다. 
  
이 섹션은 간단한 명령줄 도구 및 메서드와 고급 도구 옵션으로 나됩니다. 먼저 간단한 메서드를 다산합니다. 하지만 지금 성능 문제가 있는 경우 고급 방법으로 이동한 후 예제 성능 문제 해결 작업 계획을 시도해 보아야 합니다.
  
### <a name="simple-methods"></a>간단한 메서드

이러한 간단한 방법의 목표는 성능에 대한 정보를 알릴 수 있도록 시간이 지날 때 간단한 성능 기준을 파악하고 적절하게 저장하는 Office 365 것입니다. 다음은 이전과 같은 간단한 다이어그램입니다.
  
![클라이언트, 프록시 및 클라우드가 있는 기본 네트워크와 PSPing, TraceTCP 및 네트워크 추적을 제안하는 도구가 있습니다.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP는 요청이 대상에 도달하는 데 걸리는 네트워크 홉 수(밀리초) 및 네트워크 홉 수를 표시하는 데 유용한 도구이기 때문에 이 스크린샷에 포함되어 있습니다. TraceTCP는 홉 중에 사용되는 서버의 이름을 제공하면 지원의 Microsoft Office 365 유용할 수 있습니다. > TraceTCP 명령은 매우 간단할 수 있습니다. >> 명령에 포트 번호를 포함해야  `tracetcp.exe outlook.office365.com:443` 합니다! > [TraceTCP는](https://simulatedsimian.github.io/tracetcp_download.html) 무료 다운로드이지만 Wincap에 의존합니다. Wincap는 Netmon에서도 사용 및 설치되는 도구입니다. 또한 고급 메서드 섹션에서 Netmon을 사용할 수 있습니다. 
  
 사무실이 여러 개인 경우 각 위치에 있는 클라이언트의 데이터 집합도 유지해야 합니다. 이 테스트에서는 대기 시간을 측정합니다 Office 365. 이 경우 요청에 대한 요청을 보내는 클라이언트와 요청에 Office 365 시간 사이의 시간을 설명하는 숫자 값입니다. 테스트는 클라이언트 컴퓨터의 도메인 내부에서 시작되어 네트워크 내부에서 발신 지점을 통과하고 인터넷을 통해 왕복한 후 다시 Office 365 측정합니다. 
  
이 경우 프록시 서버인 시작 지점을 다루는 몇 가지 방법이 있습니다. 1에서 2까지 추적한 다음 2에서 3까지 추적한 다음 밀리초로 숫자를 추가하여 네트워크 가장자리에 최종 합계를 얻을 수 있습니다. 또는 주소의 프록시를 무시하도록 연결을 구성할 Office 365 있습니다. 방화벽, 역방향 프록시 또는 둘의 일부 조합이 있는 대규모 네트워크에서는 트래픽이 많은 URL에 대해 전달될 수 있도록 허용하는 프록시 서버에서 예외를 만들어야 할 수 있습니다. 2016에서 사용하는 끝점 목록은 Office 365 및 IP 주소 Office 365 를 [참조하세요.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 인증 프록시가 있는 경우 먼저 다음에 대한 예외를 테스트합니다.
  
- 포트 80 및 443
    
- TCP 및 HTTP
    
- 다음 URL로 아웃바운드된 연결:
    
- \*.microsoftonline.com
    
- \*.microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*.outlook.com
    
- \*.lync.com
    
- osub.microsoft.com
    
모든 사용자는 프록시 간섭 또는 인증 없이 이러한 주소에 액세스하도록 허용해야 합니다. 더 작은 네트워크에서 웹 브라우저의 프록시 우회 목록에 추가해야 합니다. 
  
프록시의 프록시 우회 목록에 Internet Explorer 도구  인터넷 옵션 연결 \>  \>  \> **LAN 설정** \> **고급으로 이동합니다.** 고급 탭에서는 프록시 서버 및 프록시 서버 포트도 찾을 수 있습니다. 고급 단추에 액세스하려면 **LAN에** 프록시 서버 사용 확인란을 **클릭해야 할 수** 있습니다. 로컬 주소에 프록시 서버 **무시가** 선택되어 있는지 확인할 수 있습니다. 고급을 **클릭하면** 예외를 입력할 수 있는 텍스트 상자가 표시됩니다. 위에 나열된 와일드카드 URL을 세미 콜론으로 구분합니다. 예를 들면 다음과 같습니다.
  
\*.microsoftonline.com; \*.sharepoint.com
  
프록시를 무시하고 나면 해당 URL에서 직접 ping 또는 PsPing을 사용할 Office 365 있습니다. 다음 단계는 **ping** 테스트 outlook.office365.com. 또는 PsPing 또는 명령에 포트 번호를 제공하게 하는 다른 도구를 사용하는 경우 **PsPing을** portal.microsoftonline.com:443 평균 왕복 시간을 밀리초로 볼 수 있습니다. 
  
왕복 시간(RTT)은 HTTP 요청을 서버로 보내는 데 걸리는 시간을 측정하는 숫자 값입니다 outlook.office365.com 서버가 이를 확인했다는 응답을 다시 받을 수 있습니다. 이 약어를 RTT로 표시하는 경우도 있습니다. 이 시간은 비교적 짧아야 합니다.
  
이 테스트를 실행하려면 [PSPing](/sysinternals/downloads/psping) 또는 사용자에 의해 차단되는 ICMP 패킷을 사용하지 Office 365 도구를 사용해야 합니다. 
  
 **PsPing을 사용하여 전체 왕복 시간을 전체 왕복 시간(밀리초)을 Office 365 방법**
  
1. 다음 단계를 완료하여 상승된 명령 프롬프트를 실행합니다.
    
1. **시작** 을 클릭합니다.
    
2. 검색 **시작 상자에** cmd를 입력한 다음 Ctrl+Shift+Enter를 누르고 있습니다.
    
3. 사용자 **계정** 컨트롤 대화 상자가 나타나면 표시하는 작업이 원하는 작업으로 확인된 다음 계속을 **클릭합니다.**
    
2. 도구(이 경우 PsPing)가 설치된 폴더로 이동한 후 다음 url을 Office 365 테스트합니다.
    
  - psping admin.microsoft.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![포트 443을 microsoft-my.sharepoint.com PSPing 명령입니다.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
포트 번호 443을 포함해야 합니다. 이 Office 365 암호화된 채널에서 작동합니다. 포트 번호 없이 PsPing을 사용하면 요청이 실패합니다. 짧은 목록을 ping한 후 평균 시간(밀리초)을 찾아보아야 합니다. 이는 기록하려는 것입니다!
  
![왕복 시간이 2.8밀리초인 클라이언트에서 프록시로 PSPing을 프록시하는 그림을 보여주는 그래픽입니다.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
프록시 우회에 익숙하지 않은 경우 단계별 방법을 선호하는 경우 먼저 프록시 서버의 이름을 찾아야 합니다. In Internet Explorer go to  \> **Tools Internet Options** \> **Connections** \> **LAN settings** \> **Advanced**. 고급 **탭에서** 프록시 서버가 나열됩니다. 이 작업을 완료하여 명령 프롬프트에서 프록시 서버를 Ping합니다. 
  
 **프록시 서버를 ping하고 1~2단계의 왕복 값을 밀리초(밀리초)**
  
1. 다음 단계를 완료하여 상승된 명령 프롬프트를 실행합니다.
    
1. **시작** 을 클릭합니다.
    
2. 검색 **시작 상자에** cmd를 입력한 다음 Ctrl+Shift+Enter를 누르고 있습니다.
    
3. 사용자 **계정** 컨트롤 대화 상자가 나타나면 표시하는 작업이 원하는 작업으로 확인된 다음 계속을 **클릭합니다.**
    
2. ping을 \<the name of the proxy server your browser uses, or the IP address of the proxy server\> 입력한 다음 Enter를 누를 수 있습니다. PsPing 또는 다른 도구가 설치된 경우 대신 해당 도구를 사용할 수 있습니다. 
    
    명령은 다음과 같은 예와 같을 수 있습니다. 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy:80
    
3. 추적에서 테스트 패킷 전송을 중지하면 평균(밀리초)을 나열하는 작은 요약이 표시됩니다. 프롬프트의 스크린샷을 촬영하고 이름 규칙을 사용하여 저장합니다. 이때 값을 사용하여 다이어그램을 채우는 데도 도움이 될 수 있습니다.
    
새벽에 추적을 하다가 클라이언트가 프록시(또는 인터넷으로 나가는 모든 발신 서버)에 빠르게 도착할 수 있습니다. 이 경우 번호는 다음과 같이 될 수 있습니다.
  
![클라이언트에서 프록시로의 왕복 시간을 2.8밀리초로 표시하는 그래픽입니다.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
클라이언트 컴퓨터가 프록시(또는 발신) 서버에 액세스할 수 있는 몇 가지 선택 중 하나인 경우 해당 컴퓨터에 원격으로 연결하고 명령 프롬프트를 PsPing에 실행하여 테스트의 다음 단계 중 하나를 실행할 수 Office 365 있습니다. 해당 컴퓨터에 액세스할 수 없는 경우 네트워크 리소스에 문의하여 다음 다리에 대한 도움을 받을 수 있으며 정확한 번호를 얻을 수 있습니다. 가능하지 않은 경우 해당 Office 365 URL에 대해 PsPing을 사용하여 프록시 서버에 대해 PsPing 또는 Ping 시간을 비교합니다. 
  
예를 들어 클라이언트에서 Office 365 URL까지의 51.84밀리초가 있으며 클라이언트에서 프록시(또는 발신 지점)까지의 2.8밀리초가 있는 경우, 시작부터 시작까지의 49.04밀리초가 Office 365. 마찬가지로 하루 높이 동안 클라이언트에서 프록시로의 PsPing 값이 12.25밀리초인 경우 클라이언트에서 Office 365 URL로 프록시를 62.01밀리초를 사용하는 경우 프록시가 Office 365 URL로 이동하는 평균 값은 49.76밀리초입니다.
  
![값을 빼기 위해 클라이언트에서 프록시로의 ping을 Office 365 수 있는 추가 그래픽입니다.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
문제 해결 측면에서 이러한 기준을 유지하는 것에서 흥미로운 것을 발견할 수 있습니다. 예를 들어 일반적으로 프록시 또는 전송 지점에서 40~59밀리초 정도의 대기 시간이 있는 경우 이 URL을 Office 365 있습니다. 클라이언트가 프록시 또는 발신 지점 대기 시간 약 3~7밀리초(해당 시간 동안 표시하는 네트워크 트래픽의 양에 따라 다를 수 있습니다) 프록시 또는 발신에 대한 마지막 3개의 클라이언트가 기준을 표시하는 경우 문제가 있다는 것을 확실하게 알 수 있습니다. 대기 시간(45밀리초)입니다.
  
### <a name="advanced-methods"></a>고급 메서드

네트워크 추적에 대한 인터넷 요청과 함께 Office 365 정보를 확인하려면 네트워크 추적에 익숙해지야 합니다. HTTPWatch, Netmon, 메시지 분석기, Wireshark, Fiddler, 개발자 대시보드 도구 또는 기타 추적에 선호하는 도구는 해당 도구가 네트워크 트래픽을 캡처하고 필터링할 수 있는 한 아무 도구나 상관이 없습니다. 이 섹션에서는 이러한 도구를 두 개 이상 실행하여 문제를 보다 완전한 그림으로 보는 것이 좋습니다. 테스트할 때 이러한 도구 중 일부는 자체에서 Proxies 역할을 합니다. 도우미 문서, 성능 문제 해결 계획인 Office 365 [Netmon 3.4,](https://www.microsoft.com/download/details.aspx?id=4865) [HTTPWatch](https://www.httpwatch.com/download/) [또는](performance-troubleshooting-plan.md) [WireShark를 포함합니다.](https://www.wireshark.org/)
  
성능 기준을 세우는 것은 이 방법의 간단한 부분으로, 대부분의 단계는 성능 문제를 해결할 때와 동일합니다. 성능 기준을 만드는 고급 방법을 사용하려면 네트워크 추적을 받아서 저장해야 합니다. 이 문서의 예제는 대부분 SharePoint Online을 사용하지만 테스트 및 기록을 구독하는 Office 365 서비스 전체에서 일반적인 작업 목록을 개발해야 합니다. 기준 예는 다음과 같습니다.
  
- SPO에 대한 기준 목록 - ** 1단계: ** SPO 웹 사이트의 홈 페이지를 찾아보고 네트워크 추적을 합니다. 추적을 저장합니다. 
    
- SPO에 대한 기준 목록 - **2단계:** 검색을 통해 용어(예: 회사 이름)Enterprise 검색하고 네트워크 추적을 합니다. 추적을 저장합니다. 
    
- SPO에 대한 기준 목록 - **3단계:** 업로드 온라인 문서 라이브러리에 큰 파일을 SharePoint 네트워크 추적을 합니다. 추적을 저장합니다. 
    
- SPO에 대한 기준 목록 - **4단계:** OneDrive 웹 사이트의 홈 페이지를 찾아 네트워크 추적을 합니다. 추적을 저장합니다. 
    
이 목록에는 사용자가 온라인에서 수행한 가장 중요한 일반적인 SharePoint 포함되어야 합니다. 마지막 단계에서는 비즈니스용 OneDrive 진행하는 추적을 위해 회사에서 사용자 지정하는 SharePoint Online 홈 페이지 로드와 사용자 지정되지 비즈니스용 OneDrive 홈 페이지 간의 비교를 빌드합니다. 이 테스트는 온라인 사이트의 로드 속도가 느려질 때 SharePoint 테스트입니다. 이러한 차이점에 대한 기록을 테스트에 빌드할 수 있습니다.
  
성능 문제가 있는 경우 대부분의 단계는 기준을 세울 때와 동일합니다. 네트워크 추적이 중요해지기 때문에  다음에 중요한 추적을 진행하는 방법을 처리합니다. 
  
성능 문제를 해결하려면 지금  성능 문제가 발생하면 추적을 해야 합니다. 로그를 수집하는 데 사용할 수 있는 적절한 도구를 제공해야 합니다. 즉, 수행할 수 있는 최상의 정보를 수집하기 위해 수행할 문제 해결 작업 목록과 같은 작업 계획이 필요합니다. 가장 먼저 할 일은 시간을 반영하는 폴더에 파일을 저장할 수 있도록 테스트의 날짜와 시간을 기록하는 것입니다. 그런 다음 문제 단계로 좁혀야 합니다. 테스트에 사용할 정확한 단계입니다. 기본 사항도 잊지 마세요. 문제가 Outlook 서비스에서만 문제 동작이 발생하는지 기록해야 Office 365. 이 문제의 범위를 좁히면 해결할 수 있는 점에 집중하는 데 도움이 됩니다. 
  
## <a name="see-also"></a>참고 항목

[Office 365 끝점 관리](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)