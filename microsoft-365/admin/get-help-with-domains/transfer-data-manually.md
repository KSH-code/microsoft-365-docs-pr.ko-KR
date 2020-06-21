---
title: 두 계정 간에 데이터를 수동으로 전송
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 계획 또는 회사 이름을 변경 했을 때 두 Microsoft 365 계정 간에 데이터를 수동으로 전송 하거나 여러 구독을 하나로 결합 하는 방법을 알아봅니다.
ms.openlocfilehash: 6e64872ad7e145b63eb71d89ea2d69e5d8697eb6
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780172"
---
# <a name="transfer-data-manually-between-two-accounts"></a>두 계정 간에 데이터를 수동으로 전송

Sleeves을 롤업 하 고 일정에서 시간을 차단: 두 Microsoft 365 계정 간에 데이터를 전송 하는 것은 수동, 복잡 및 시간이 많이 걸리는 프로세스입니다. 자동 또는 지원 되는 프로세스가 아닙니다. 시작 하는 것이 좋습니다.
  
> [!CAUTION]
> 전자 메일, 비즈니스용 Skype 및 Microsoft 365에서 호스트 되는 공개 웹 사이트가 작동 하는 동안 문제가 발생 하 게 됩니다. 사용자는 새 사용자 이름과 암호를 얻게 되며 Outlook을 다시 설정 해야 합니다.

**다음 중 하나가 적용 될 경우이 항목의 지침을 사용 하 여 데이터를 수동으로 전송 하기만 하면 됩니다.**
  
- 다른 서비스 제품군의 요금제로 변경 해야 합니다.

- 회사 이름이 변경 되었으며, 다른 초기 도메인 이름을 사용 하기 때문에 새 구독을 만들고 데이터를 마이그레이션하기를 결정 했습니다.

- 여러 구독을 하나의 새 구독과 결합 해야 합니다.

> [!IMPORTANT]
> [구독 계획을 변경](../../commerce/subscriptions/switch-to-a-different-plan.md) 해야 하 고 요금제 전환 마법사를 사용할 수 있는 경우 또는 요금제 전환 마법사가 작동 하지 않더라도 동일한 구독 패밀리에서 새 구독 계획으로 전송 해야 하는 경우에는 데이터를 수동으로 전송할 필요가 없으며,이 경우에는 가동 중지 시간이 없습니다.

|**Tasks**|**Steps**|
|:-----|:-----|
|이동 하려는 계획을 구입 합니다.  <br/> |등록할 때 초기 도메인 이름에 사용할 회사 *이름 (예: onmicrosoft.com* , public.sharepoint.com 및 *sharepoint.com)을* 지정 *합니다.* 기존 구독에 사용한 것과는 다른 *회사* 이름을 사용 해야 합니다.  <br/> > [!NOTE]>은 일반적으로 구독을 취소 한 후 몇 개월 동안 시스템에서 해당 *회사* 를 사용 하는 초기 도메인 이름을 해제 하는 데 소요 됩니다. 이전 Microsoft 365 구독의 모든 데이터를 저장 하 고 해당 구독을 취소 하더라도 새 구독에서 이전 *회사* 가치를 즉시 사용할 수 없습니다.           |
|이전 Microsoft 365 구독에서 사용자 지정 도메인을 제거 합니다.  <br/> | [도메인을 제거 하기 전에 필요한 단계](remove-a-domain.md) 에 따라 사용자 전자 메일 주소에서 도메인 이름을 제거 하 고 사용자 지정 도메인에 대 한 전자 메일 및 LYNC 용 DNS 레코드를 제거 합니다. Microsoft 365에서 공개 웹 사이트를 호스트 하는 경우에는이를 가리키는 CNAME 레코드도 제거 해야 합니다.  <br/> > [!IMPORTANT]>이 사용자 지정 도메인으로 전자 메일을 라우팅하는 MX 레코드를 제거한 후 새 계정에 도메인을 추가 하 고 새 MX 레코드를 설정 하 고 사용자를 설정할 때까지 전자 메일이 제대로 작동 하지 않습니다. Lync에 대 한 DNS 레코드를 제거 하면 Lync가 작동 하지 않습니다. 또한 공개 웹 사이트를 가리키는 CNAME 레코드를 제거한 후에는 사용할 수 없습니다.           [도메인을 제거](remove-a-domain.md) 합니다.  <br/> |
|새 구독에 대 한 사용자 지정 도메인을 설정 하 고 사용자를 설정 합니다.  <br/> | 사용자 지정 도메인에 필요한 DNS 레코드를 만드는 작업을 포함 하 여 새 구독을 설정 합니다.  <br/>  사용자 지정 도메인에 전자 메일 주소를 사용 하 여 사용자를 만듭니다.  <br/> |
|이전 구독에서 새 구독으로 데이터를 전송 합니다.  <br/> | 별도의 브라우저 창에서 두 계정에 로그인 합니다.  <br/>  Internet Explorer 아이콘을 마우스 오른쪽 단추로 클릭 하 고 두 개의 InPrivate 브라우저 창을 엽니다. 두 windows에서 다른 자격 증명을 사용 하 여 두 계정 모두에 로그인 할 수 있습니다.  <br/> [구독 간 관리 설정 전송](#email) <br/> [팀 사이트 구조 및 데이터 전송](#transfer-team-site-structure-and-data) <br/> [구독 간 공용 웹 사이트 전송](#transfer-a-public-website-between-subscriptions) <br/> [구독 간 관리 설정 전송](#email) <br/> |
|Microsoft 365에 대 한 Microsoft 지원 서비스를 호출 하 여 완료 한 계획에 대 한 구독을 취소 합니다.  <br/> | 새 구독이 작동 하며 모든 데이터가 전송 되었는지 확인 합니다.  <br/>  [고객 지원에 문의](../contact-support-for-business-products.md) 하 여 이전 구독을 취소 합니다.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>구독 간 관리 설정 전송

각 계정의 다음 페이지로 이동 하 여 이전 계정의 설정을 기반으로 새 계정을 설정 합니다.
  
Microsoft 365에서 Microsoft 365 중소 Business 또는 Microsoft 365 Enterprise로 데이터를 전송 하는 경우 관리 페이지는 서로 다른 방식으로 구성 됩니다. 비디오 시청 [: Microsoft 365 Enterprise를 소개](https://docs.microsoft.com/microsoft-365/admin/)하 고 다음 위치로 이동 하 여 관리 설정을 확인 하세요.
  
Microsoft 365 Enterprise 및 Microsoft 365 중소 Business:
  
|**위치**|**용도**|
|:-----|:-----|
|**관리자** \> **Microsoft 365** \> **서비스 설정** <br/> |메일, 사이트, Lync, 사용자 소프트웨어, 암호, 커뮤니티, 권한 관리 및 모바일의 설정에 대 한 각 탭을 선택 합니다.  <br/> |
|**관리자** \> **Exchange** <br/> | Exchange Online 설정  <br/> |
|**관리자** \> **SharePoint** <br/> | SharePoint Online 설정  <br/> |
|**관리자** \> **비즈니스용 Skype** <br/> |추가 비즈니스용 Skype 설정  <br/> |

Microsoft 365 Small Business
  
|**위치**|**용도**|
|:-----|:-----|
|**관리자** \> **조직 수준 설정 관리** <br/> |관리 설정  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>구독 간 공용 웹 사이트 전송

Microsoft 365에서 호스트 되는 공개 웹 사이트가 있는 경우이를 저장 하 고 새 구독에 다시 만들어야 합니다.
  
> [!NOTE]
> 공용 웹 사이트가 DNS 호스팅 공급자에 호스트 되는 경우에는 변경이 필요 하지 않습니다. 전환의 영향을 받지 않습니다.
  
문서 라이브러리 또는 목록 콘텐츠를 SharePoint Online 환경에서 파일 공유 또는 로컬 컴퓨터로 저장 하려면 [Sharepoint online 콘텐츠 수동 마이그레이션을](https://go.microsoft.com/fwlink/p/?LinkId=402910)참조 하세요.
  
> [!NOTE]
> 공용 사이트 마이그레이션 앱에서 데이터를 다른 구독으로 전송할 수 없습니다.
  
## <a name="transfer-team-site-structure-and-data"></a>팀 사이트 구조 및 데이터 전송

팀 사이트 데이터를 저장 하거나 전송 하는 방법에는 여러 가지가 있습니다.
  
- 이전 사이트를 서식 파일로 저장 하 고 서식 파일을 새 사이트로 가져올 수 있습니다.

- 문서를 전송 하려면 먼저 새 사이트에서 계층 구조를 수동으로 다시 만듭니다. 그런 다음 두 SharePoint 팀 사이트를 동시에 열고 Windows 탐색기를 사용 하 여 두 문서 라이브러리를 열고 문서를 복사 하 여 붙여 넣을 수 있습니다. [비디오: Explorer에서 열기를 사용 하 여 라이브러리 파일 복사 또는 이동을](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)참조 하세요.

- 목록 데이터를 전송 하려면 [목록 서식 파일](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)을 저장 하 고 저장 된 서식 파일을 사용 하 여 새 사이트에 목록을 다시 만듭니다.

- SharePoint Online 환경 (비즈니스용 OneDrive 또는 팀 사이트)의 문서 라이브러리 또는 목록 콘텐츠를 파일 공유 또는 로컬 컴퓨터에 저장 하려면 [Sharepoint online 콘텐츠의 수동 마이그레이션에 대 한 정보](https://support.microsoft.com/kb/2783484)를 참조 하세요.

## <a name="transfer-users-data-between-subscriptions"></a>구독 간 사용자 데이터 전송

### <a name="email"></a>메일 주소:

새 구독을 설정한 후 사용자에 게 [전자 메일, 연락처, 작업 및 일정 정보를 이동](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) 하도록 요청 합니다. Sue@contoso.onmicrosoft.com와 같은 초기 사용자 이름을 사용 하 여 이전 전자 메일에 액세스할 수 있습니다.
  
### <a name="onedrive-for-business-data"></a>비즈니스용 OneDrive 데이터:

사용자에 게 [비즈니스용 OneDrive 콘텐츠를 컴퓨터에](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)복사/동기화 하도록 요청 하 고 새 구독에 다시 추가 합니다.
