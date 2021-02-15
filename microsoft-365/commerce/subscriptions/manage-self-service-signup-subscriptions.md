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
description: 조직에 대한 무료 셀프 서비스 등록 구독을 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376308"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>셀프 서비스 등록 구독 관리

## <a name="what-are-self-service-sign-up-subscriptions"></a>셀프 서비스 등록 구독이란?

조직의 사용자가 등록할 수 있는 무료 셀프 서비스 등록 구독은 제한되어 있습니다. 사용자는 셀프 서비스 등록 구독에만 등록하고 사용할 수 있습니다. 사용자 등록을 차단하고 사용자가 등록한 무료 구독을 삭제하여 셀프 서비스 등록 구독을 관리합니다. 셀프 서비스 등록 및 사용 가능한 구독에 대한 자세한 내용은 조직에서 셀프 서비스 등록 사용을 [참조하세요.](../../admin/misc/self-service-sign-up.md)

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>셀프 서비스 등록 구독 목록 보기

1. 관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.
2. 제품 **탭에서** 필터 아이콘을 선택한 다음 무료를 **선택합니다.** 모든 셀프 서비스 등록 구독 목록이 표시됩니다.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>이러한 구독은 셀프 서비스 구매 구독과 어떻게 다른가요?

셀프 서비스 등록 구독은 무료이며 셀프 서비스 구매 구독보다 더 큰 제품 목록에서 사용할 수 있습니다. 사용자가 셀프 서비스 구매 구독에 등록하면 해당 구독 비용을 지불해야 합니다. 셀프 서비스 구매 구독은 Power Platform 제품(Power BI, Power Apps 및 Power Automate), Project 및 Visio에서만 사용할 수 있습니다. 자세한 내용은 셀프 서비스 [구매 FAQ를 참조하세요.](self-service-purchase-faq.md)

## <a name="block-users-from-signing-up"></a>사용자의 등록 차단

**AllowAdHocSubscriptions** 매개 변수와 함께 [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) cmdlet을 사용하여 사용자가 셀프 서비스 등록에 등록할 수 있는지 여부를 제어할 수 있습니다. 자세한 내용은 셀프 [서비스 설정을 제어하는 방법을 참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>셀프 서비스 등록 구독 삭제

> [!IMPORTANT]
> 셀프 서비스 등록 구독을 삭제하면 모든 사용자가 데이터 및 전자 메일에 액세스하지 못하게 차단하고 모든 데이터와 전자 메일을 삭제합니다.

1. 관리 센터에서 **빌링** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a>페이지로 이동합니다.
2. 제품 **탭에서** 필터 아이콘을 선택한 다음 무료를 **선택합니다.**
3. 삭제할 셀프 서비스 등록 구독을 선택합니다. 
4. 구독 세부 정보 페이지의 구독 및 **결제** 설정 섹션에서 구독 **삭제를 선택합니다.**
5. 구독 **삭제 창에서** 확인란을 선택한 다음 구독 **삭제를 선택합니다.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>디렉터리를 지우는 셀프 서비스 등록 구독이 있습니다.

개별 사용자가 등록할 수 있는 셀프 서비스 등록 제품도 Azure AD 디렉터리에서 인증을 위한 게스트 사용자를 만들 수 있습니다. 데이터 손실을 방지하기 위해 이러한 셀프 서비스 제품은 디렉터리에서 완전히 삭제될 때까지 디렉터리 삭제를 차단합니다. Azure AD 관리자만 삭제할 수 있습니다. 자세한 내용은 [Azure Active Directory에서 디렉터리 삭제를 참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)