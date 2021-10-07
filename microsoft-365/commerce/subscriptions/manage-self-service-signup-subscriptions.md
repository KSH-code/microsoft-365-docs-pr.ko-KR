---
title: 셀프 서비스 등록 구독 관리
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: 조직의 무료 셀프 서비스 등록 구독을 관리하는 방법에 대해 자세히 알아보습니다.
ms.date: 03/17/2021
ms.openlocfilehash: 24f852a1eb9983e211000b59bda32eaa2c6bf0fa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192382"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>셀프 서비스 등록 구독 관리

## <a name="what-are-self-service-sign-up-subscriptions"></a>셀프 서비스 등록 구독이란?

조직의 사용자가 등록할 수 있는 무료 셀프 서비스 등록 구독은 제한되어 있습니다. 사용자는 셀프 서비스 등록 구독에만 등록하고 사용할 수 있습니다. 사용자의 등록을 차단하고 사용자가 등록한 무료 구독을 삭제하여 셀프 서비스 등록 구독을 관리합니다. 셀프 서비스 등록 및 사용 가능한 구독에 대한 자세한 내용은 [조직에서 셀프](../../admin/misc/self-service-sign-up.md)서비스 등록 사용을 참조하세요.

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>셀프 서비스 등록 구독 목록 보기

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 페이지로 이동하세요.
2. 제품 **탭에서** 필터 아이콘을 선택한 다음 무료 를 **선택합니다.** 모든 셀프 서비스 등록 구독 목록이 표시됩니다.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>이러한 구독은 셀프 서비스 구매 구독과 어떻게 다른가요?

셀프 서비스 등록 구독은 무료이며 셀프 서비스 구매 구독보다 더 큰 제품 목록에서 사용할 수 있습니다. 사용자가 셀프 서비스 구매 구독에 등록하면 해당 구독 비용을 지불해야 합니다. 셀프 서비스 구매 구독은 Power Platform 제품(Power BI, Power Apps 및 Power Automate), Project 및 Visio 사용할 수 Visio. 자세한 내용은 셀프 서비스 [구매 FAQ 를 참조하세요.](self-service-purchase-faq.yml)

## <a name="block-users-from-signing-up"></a>사용자의 등록 차단

[**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet을 **AllowAdHocSubscriptions** 매개 변수와 함께 사용하여 사용자가 셀프 서비스 등록 구독에 등록할 수 있는지 여부를 제어할 수 있습니다. 자세한 내용은 [셀프 서비스 설정을 제어하는 방법을 참조하세요.](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>셀프 서비스 등록 구독 삭제

> [!IMPORTANT]
> 셀프 서비스 등록 구독을 삭제하면 모든 사용자가 데이터 및 전자 메일에 액세스하지 못하게 차단하고 모든 데이터와 전자 메일을 삭제합니다.

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 페이지로 이동하세요.
2. 제품 **탭에서** 필터 아이콘을 선택한 다음 무료 를 **선택합니다.**
3. 삭제할 셀프 서비스 등록 구독을 선택합니다. 
4. 구독 세부 정보 페이지의 구독  및 결제 설정 섹션에서 구독 **삭제를 선택합니다.**
5. 구독 **삭제 창에서** 확인란을 선택한 다음 구독 **삭제 를 선택합니다.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>디렉터리를 지우는 셀프 서비스 등록 구독이 있습니다.

개별 사용자가 등록할 수 있는 셀프 서비스 등록 제품도 Azure AD 디렉터리에서 인증을 위해 게스트 사용자를 만들 수 있습니다. 데이터 손실을 방지하기 위해 이러한 셀프 서비스 제품은 디렉터리에서 완전히 삭제될 때까지 디렉터리 삭제를 차단합니다. Azure AD 관리자만 삭제할 수 있습니다. 자세한 내용은 [Delete a directory in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-delete-howto)
