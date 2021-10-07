---
title: Microsoft 365에서 격리 및 액세스 제어
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: '요약: 다양한 응용 프로그램 내에서의 고리 및 액세스 제어에 대한 Microsoft 365.'
ms.openlocfilehash: ba40efbacac849e2228455697c43da45b2bcbe47
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197308"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Microsoft 365에서 격리 및 액세스 제어

Azure Active Directory(Azure AD) 및 Microsoft 365 서비스, 수백 개의 엔터티, 수천 개의 관계 및 수만 개의 특성을 포함하는 매우 복잡한 데이터 모델을 사용 합니다. 높은 수준에서 Azure AD 및 서비스 감독은 테넌트 및 받는 사람의 컨테이너가 상태 기반 복제 프로토콜을 사용하여 동기화된 상태로 유지됩니다. Azure AD 내에 있는 디렉터리 정보 외에도 각 서비스 워크로드에는 자체 디렉터리 서비스 인프라가 있습니다.
 
![Microsoft 365 데이터 동기화를 저장합니다.](../media/office-365-isolation-tenant-data-sync.png)

이 모델에는 디렉터리 데이터의 원본이 하나도 없습니다. 특정 시스템은 개별 데이터를 소유하지만 단일 시스템에서는 모든 데이터를 보유하지 않습니다. Microsoft 365 서비스는 이 데이터 모델에서 Azure AD와 협력합니다. Azure AD는 공유 데이터에 대한 "참 시스템"으로, 일반적으로 모든 서비스에서 사용하는 작고 정적 데이터입니다. Azure AD와 Azure AD에서 사용되는 Microsoft 365 공유 보기를 제공합니다.

Microsoft 365 저장소와 Azure 클라우드 저장소를 모두 사용하게 됩니다. Exchange Online(Exchange Online Protection 포함) 및 비즈니스용 Skype 자체 저장소를 사용하여 고객 데이터를 저장합니다. SharePoint 온라인에서는 SQL Server 저장소와 Azure Storage 모두 사용하게 되어 저장소 수준에서 고객 데이터를 추가로 따로 따로 보관해야 합니다.

## <a name="exchange-online"></a>Exchange Online

Exchange Online 사서함에 고객 데이터를 저장하는 데 사용할 수 있습니다. 사서함은 사서함 데이터베이스라는 ESE(Extensible Storage Engine) 데이터베이스 내에서 호스트됩니다. 여기에는 사용자 사서함, 연결된 사서함, 공유 사서함 및 공용 폴더 사서함이 포함됩니다. 사용자 사서함에는 대화 내용과 비즈니스용 Skype 저장된 콘텐츠가 포함됩니다.

사용자 사서함 콘텐츠에는 다음이 포함됩니다.

- 전자 메일 및 전자 메일 첨부 파일
- 일정 및 약속이 있는/약속이 있는 정보
- 연락처
- 작업
- 참고
- 그룹
- 유추 데이터

데이터베이스 내의 각 Exchange Online 여러 테넌트의 사서함이 포함되어 있습니다. 권한 부여 코드는 테넌시 내에서를 포함하여 각 사서함을 보호합니다. 기본적으로 할당된 사용자만 사서함에 액세스할 수 있습니다. 사서함을 보호하는 ACL(액세스 제어 목록)에는 테넌트 수준에서 Azure AD에서 인증한 ID가 포함되어 있습니다. 각 테넌트의 사서함은 테넌트의 인증 공급자에 대해 인증된 ID로 제한됩니다. 여기에는 해당 테넌트의 사용자만 포함됩니다. 테넌트 A의 콘텐츠는 테넌트 A가 명시적으로 승인하지 않는 한 테넌트 B의 사용자가 어떤 방식으로도 얻을 수 없습니다.

## <a name="skype-for-business"></a>비즈니스용 Skype

비즈니스용 Skype 장소에 데이터를 저장하는 데 사용할 수 있습니다.

- 연결 끝점, 테넌트 ID, 다이얼 플랜, 로밍 설정, 현재 상태, 연락처 목록 등을 포함하는 사용자 및 계정 정보는 비즈니스용 Skype Active Directory 서버 및 다양한 비즈니스용 Skype 데이터베이스 서버에 저장됩니다. 연락처 목록은 사용자가 두 제품 모두에 Exchange Online 경우 사용자의 비즈니스용 Skype 사서함에 저장됩니다. 비즈니스용 Skype 데이터베이스 서버는 테넌트당 분할되지 않지만 다중 테넌시 데이터 구분은 RBAC(역할 기반 액세스 제어)를 통해 적용됩니다.
- 모임 콘텐츠 및 업로드된 데이터는 DFS(분산 파일 시스템) 공유에 저장됩니다. 이 콘텐츠를 사용하도록 설정한 경우 콘텐츠에 Exchange Online 수 있습니다. DFS 공유는 테넌트당 분할되지 않습니다. 콘텐츠가 ACL로 보호됩니다. 다중 테넌시가 RBAC를 통해 적용됩니다.
- 통화 기록, IM 세션, 응용 프로그램 공유, IM 기록 등의 활동 기록인 통화 정보 기록은 Exchange Online 저장할 수도 있지만 대부분의 통화 정보 기록은 CDR(통화 정보 기록) 서버에 일시적으로 저장됩니다. 콘텐츠는 테넌트당 분할되지 않지만 다중 테넌시가 RBAC를 통해 적용됩니다.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint 온라인에는 데이터 분리를 제공하는 여러 독립적인 메커니즘이 있습니다. 응용 프로그램 데이터베이스 내에 개체를 추상화 코드로 저장합니다. 예를 들어 사용자가 SharePoint Online에 파일을 업로드하면 파일이 분해되고 응용 프로그램 코드로 변환되어 여러 데이터베이스의 여러 테이블에 저장됩니다.

사용자가 데이터가 포함된 저장소에 직접 액세스할 수 있는 경우 콘텐츠가 온라인이 아닌 다른 시스템이나 사람이 해석할 SharePoint 없습니다. 이러한 메커니즘에는 보안 액세스 제어 및 속성이 포함됩니다. 모든 SharePoint Online 리소스는 테넌시 내에서를 포함하여 인증 코드 및 RBAC 정책에 의해 보호됩니다. 리소스를 보호하는 ACL(액세스 제어 목록)에는 테넌트 수준에서 인증된 ID가 포함되어 있습니다. SharePoint 테넌트의 온라인 데이터는 테넌트에 대한 인증 공급자가 인증한 ID로 제한됩니다.

ACL 외에도 인증 공급자(테넌트별 Azure AD)를 지정하는 테넌트 수준 속성이 한 번 작성되어 설정된 후 변경할 수 없습니다. 테넌트에 대해 인증 공급자 테넌트 속성이 설정되면 테넌트에 노출된 API를 사용하여 변경할 수 없습니다.

각 *테넌트에* 대해 고유한 SubscriptionId가 사용됩니다. 모든 고객 사이트는 테넌트가 소유하고 테넌트에 고유한 *SubscriptionId가* 할당됩니다. 사이트의 *SubscriptionId* 속성은 한 번 작성된 후 영구적입니다. 테넌트에 할당된 사이트는 다른 테넌트로 이동할 수 없습니다. *SubscriptionId는* 인증 공급자에 대한 보안 범위를 만드는 데 사용되는 키로, 테넌트에 따라 다릅니다.

SharePoint 온라인에서는 콘텐츠 SQL Server 저장소에 Azure Storage 및 데이터를 사용할 수 있습니다. 콘텐츠 저장소의 파티션 키는 콘텐츠 저장소의 *SiteId* SQL. SQL 쿼리를 SharePoint Online에서는 테넌트 수준 *SubscriptionId* 확인의 일부로 확인된 *SiteId를* 사용합니다.

SharePoint 온라인에서는 암호화된 파일 콘텐츠를 blob에 Microsoft Azure 저장합니다. 각 SharePoint Online 팜에는 자체 Microsoft Azure 계정이 있으며 Azure에 저장된 모든 Blob은 해당 콘텐츠 저장소에 저장된 키로 SQL 암호화됩니다. 코드에서 인증 계층에 의해 보호되어 최종 사용자에게 직접 노출되지 않는 암호화 키입니다. SharePoint 온라인에는 HTTP 요청이 두 개 이상의 테넌트에 대한 데이터를 읽거나 쓰는 경우를 감지하는 실시간 모니터링이 있습니다. 요청 ID *SubscriptionId는* 액세스한 리소스의 *SubscriptionId에* 대해 추적됩니다. 최종 사용자가 두 개 이상의 테넌트의 리소스에 액세스하는 요청은 절대 발생하면 안 됩니다. 다중 테넌트 환경의 서비스 요청만 예외입니다. 예를 들어 검색 크롤러는 전체 데이터베이스에 대한 콘텐츠 변경 내용을 한 번씩 끌어오는 경우를 예로 들 수 있습니다. 일반적으로 단일 서비스 요청에서 두 개 이상의 테넌트의 사이트를 쿼리하는 작업과 관련이 있습니다. 이는 효율성을 위해 수행됩니다.

## <a name="teams"></a>Teams

사용자 Teams 콘텐츠 형식에 따라 다르게 저장됩니다. 

자세한 설명은 Microsoft Teams 아키텍처에서 [Ignite breakout](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) 세션을 확인 합니다.

### <a name="core-teams-customer-data"></a>핵심 Teams 고객 데이터

테넌트가 오스트레일리아, 캐나다, 유럽 연합, 프랑스, 독일, 인도, 일본, 남아프리카 공화국, 대한민국, 스위스(리히텐스테인 포함), 아랍에미리트, 영국 또는 미국에 프로비전된 경우 Microsoft는 다음 고객 데이터를 해당 위치 내에서만 저장합니다.

- Teams, 팀 및 채널 대화, 이미지, 음성 메일 메시지 및 연락처를 제공합니다.
- SharePoint Online 사이트 콘텐츠 및 해당 사이트 내에 저장되어 있는 파일
- 직장 또는 OneDrive 파일로 업로드된 파일입니다.

#### <a name="chat-channel-messages-team-structure"></a>채팅, 채널 메시지, 팀 구조

모든 팀 Teams 그룹 및 Microsoft 365 사이트 및 SharePoint 사서함의 Exchange 합니다. 비공개 채팅(그룹 채팅 포함), 채널에서 대화의 일부로 전송되는 메시지 및 팀과 채널의 구조는 Azure에서 실행되는 채팅 서비스에 저장됩니다. 또한 이 데이터는 정보 보호 기능을 사용할 수 있도록 사용자 및 그룹 사서함의 숨겨진 폴더에 저장됩니다.

#### <a name="voicemail-and-contacts"></a>음성 메일 및 연락처

음성메일은 음성 Exchange. 연락처는 Exchange 클라우드 데이터 저장소에 저장됩니다. Exchange 및 Exchange 기반 클라우드 저장소는 이미 각 전 세계 데이터 센터 지리적 위치의 데이터 상주를 제공합니다. 모든 팀의 경우 음성 메일 및 연락처는 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 남아프리카 공화국, 대한민국, 스위스(리히텐스테인 포함) 및 미국에 대해 국내에 저장됩니다. 다른 모든 국가의 경우 파일은 테넌트에 따라 미국, 유럽 또는 Asia-Pacific 위치에 저장됩니다.

#### <a name="images-and-media"></a>이미지 및 미디어

채팅에 사용되는 미디어(저장되지는 않지만 원래 Giphy 서비스 URL에 대한 참조 링크인 Giphy GIF를 제외하고, Giphy는 Microsoft가 아닌 서비스임)는 채팅 서비스와 동일한 위치에 배포되는 Azure 기반 미디어 서비스에 저장됩니다.

#### <a name="files"></a>파일

채널에서 누군가 공유하는 파일(OneNote 및 위키 포함)은 팀의 사이트 SharePoint 저장됩니다. 모임 또는 통화 중에 비공개 채팅 또는 채팅에서 공유되는 파일은 파일을 공유하는 사용자의 OneDrive 또는 학교 계정에 대한 파일로 업로드되고 저장됩니다. Exchange, SharePoint 및 OneDrive 전 세계 데이터 센터 지리적 위치의 데이터 상주를 이미 제공합니다. 따라서 기존 고객의 경우 모든 파일, OneNote 전자 필기장, Teams 위키 콘텐츠 및 Teams 환경의 일부인 사서함은 테넌트 관련성에 따라 위치에 이미 저장되어 있습니다. 파일은 호주, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 남아프리카 공화국, 대한민국 및 스위스(리히텐스테인 포함)에 대한 국내에 저장됩니다. 다른 모든 국가의 경우 파일은 테넌트에 따라 미국, 유럽 또는 아시아 태평양 위치에 저장됩니다.
