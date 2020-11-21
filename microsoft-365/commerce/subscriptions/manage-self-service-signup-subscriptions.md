---
title: 셀프 서비스 등록 구독 관리
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 조직에 대 한 무료 셀프 서비스 등록 구독을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376308"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>셀프 서비스 등록 구독 관리

## <a name="what-are-self-service-sign-up-subscriptions"></a>셀프 서비스 등록 구독은 무엇입니까?

조직의 사용자가 등록할 수 있는 제한 된 수의 무료 셀프 서비스 등록 구독이 제공 됩니다. 사용자는 자체적으로 셀프 서비스 등록 구독을 등록 하 고 사용할 수만 있습니다. 사용자가 등록 하지 못하도록 차단 하 고 사용자가 등록 한 무료 구독을 삭제 하 여 셀프 서비스 등록 구독을 관리 합니다. 셀프 서비스 등록 및 사용 가능한 구독에 대 한 자세한 내용은 [조직에서 셀프 서비스 등록 사용](../../admin/misc/self-service-sign-up.md)을 참조 하십시오.

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>셀프 서비스 등록 구독 목록 보기

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 페이지로 이동하세요.
2. **제품** 탭에서 필터 아이콘을 선택한 다음 **사용 가능** 을 선택 합니다. 모든 셀프 서비스 등록 구독 목록이 표시 됩니다.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>이러한 구독은 셀프 서비스 구매 구독과 어떤 차이가 있나요?

셀프 서비스 등록 구독은 무료 이며 셀프 서비스 구매 구독 보다 더 큰 제품 목록에서 사용할 수 있습니다. 사용자가 셀프 서비스 구매 구독을 등록 하는 경우이에 대 한 지불을 담당 하 게 됩니다. 셀프 서비스 구매 구독은 전원 플랫폼 제품 (Power BI, 파워 앱, 전원 자동화), 프로젝트 및 Visio에만 사용할 수 있습니다. 자세한 내용은 [셀프 서비스 구매 FAQ](self-service-purchase-faq.md)를 참조 하세요.

## <a name="block-users-from-signing-up"></a>사용자의 등록 차단

**AllowAdHocSubscriptions** 매개 변수와 함께 [**set-msolcompanysettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) cmdlet을 사용 하 여 사용자가 셀프 서비스 등록 구독에 등록할 수 있는지 여부를 제어 합니다. 자세한 내용은 [How to control services settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings) 를 참조 하십시오.

## <a name="delete-a-self-service-sign-up-subscription"></a>셀프 서비스 등록 구독 삭제

> [!IMPORTANT]
> 셀프 서비스 등록 구독을 삭제 하면 모든 사용자가 해당 데이터 및 전자 메일에 액세스할 수 없도록 차단 되며 모든 데이터 및 전자 메일을 삭제 합니다.

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 페이지로 이동하세요.
2. **제품** 탭에서 필터 아이콘을 선택한 다음 **사용 가능** 을 선택 합니다.
3. 삭제 하려는 셀프 서비스 등록 구독을 선택 합니다. 
4. 구독 정보 페이지의 **구독 및 결제 설정** 섹션에서 **구독 삭제** 를 선택 합니다.
5. **구독 삭제** 창에서 확인란을 선택 하 고 **구독 삭제** 를 선택 합니다.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>디렉터리 삭제를 차단 하는 셀프 서비스 등록 구독을 사용 하는 경우

개별 사용자가 등록할 수 있는 셀프 서비스 등록 제품은 Azure AD 디렉터리에서 인증을 위한 게스트 사용자도 만듭니다. 데이터 손실을 방지 하기 위해 이러한 셀프 서비스 제품은 디렉터리 삭제를 중단 하 고 디렉터리가 완전히 삭제 될 때까지이를 차단 합니다. Azure AD 관리자만 이러한 사용자를 삭제할 수 있습니다. 자세한 내용은 [Azure Active directory에서 디렉터리 삭제](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)를 참조 하세요.