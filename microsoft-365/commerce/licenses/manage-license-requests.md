---
title: 라이선스 요청 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: 비즈니스용 구독에 대한 사용자 라이선스 요청을 검토하고 승인하거나 거부하는 Microsoft 365 방법을 알아보습니다.
ms.date: 06/07/2021
ms.openlocfilehash: 279894f8e6ffb3209a1b4f2a5201e62428f33b83
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179670"
---
# <a name="manage-license-requests"></a>라이선스 요청 관리

> [!NOTE]
> 이 문서의 정보는 셀프 서비스 구매 제품에만 적용됩니다. 자세한 내용은 셀프 서비스 [구매 FAQ 를 참조합니다.](../subscriptions/self-service-purchase-faq.yml)

조직에서 셀프 서비스 구매를 사용하지 않도록 설정한 경우 라이선스 요청을 사용하여 사용자의 라이선스 요청 프로세스를 관리할 수 있습니다. 사용자가 차단한 제품에 대해 셀프 서비스 구매를 만들 때 라이선스 요청을 관리자에게 제출할 수 있습니다. 사용자가 요청을 할 때 제품에 대한 라이선스도 필요한 다른 사용자의 이름을 추가할 수 있습니다.

> [!NOTE]
> 사용자가 셀프 서비스 구매를 하지 못하게 차단하면 Microsoft는 마케팅 전자 메일을 보내지 않습니다. 또한 제품의 평가판을 사용하는 경우 구입하라는 메시지가 표시되지 않습니다. 자세한 내용은 [Manage self-service purchases (Admin)를 참조하세요.](../subscriptions/manage-self-service-purchases-admins.md)

라이선스 요청을 보고 관리하기 위해  관리자는 라이선스 페이지의 요청 **탭을** 사용합니다. 이 목록에는 요청된 제품의 이름, 라이선스를 요청하는 사람의 이름, 요청한 날짜 및 요청의 상태가 표시됩니다. 관리자는 목록을 필터링하여 보류 중 또는 완료된 요청을 표시할 수 있습니다. 요청은 30일 동안 진행됩니다.

## <a name="before-you-begin"></a>시작하기 전에

이 문서의 작업을 수행하려면 전역 관리자 되어야 합니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="use-your-own-request-process"></a>자체 요청 프로세스 사용

조직에 자체 요청 프로세스가 있는 경우 대신 사용할 수 있습니다. 사용자가 라이선스를 요청할 때 표시되는 메시지를 만들 수 있습니다.

> [!IMPORTANT]
> 자체 요청 프로세스를 사용하는 경우 요청 탭에 요청이 **표시되지** 않습니다. 메시지를 추가하기 전의 기존 요청은 승인하거나 거부할 때까지 계속 표시됩니다.

1. 관리 센터에서 청구 라이선스 페이지로  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">이동한</a> 다음 요청 **탭을** 선택합니다.
2. 대신 **기존 요청 프로세스 사용을 선택합니다.**
3. 오른쪽 창의 메시지 상자에 사용자가 라이선스를 요청할 때 보게 할 메시지를 입력합니다.  조직 정책 또는 기타 설명서에 대한 링크도 포함하려면 설명서 링크(선택 **사항)** 텍스트 상자에 URL을 입력합니다.
4. **저장** 을 선택합니다.

요청 **목록으로 돌아오면** 자체 라이선스 요청 프로세스를 사용 중입니다.는 메시지가 **표시됩니다.** 사용자에게 전송된 메시지를 변경하려면 대신 기존 요청 프로세스 **사용을 선택합니다.**

## <a name="stop-using-your-own-request-process"></a>자체 요청 프로세스 사용 중지

1. 관리 센터에서 청구 라이선스 페이지로  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">이동한</a> 다음 요청 **탭을** 선택합니다.
2. 대신 **기존 요청 프로세스 사용을 선택합니다.**
3. 오른쪽 창에서 조직의 요청 프로세스 사용 **확인란의 선택을** 취소합니다.
4. **저장** 을 선택합니다.

## <a name="approve-or-deny-a-license-request"></a>라이선스 요청 승인 또는 거부

1. 관리 센터에서 청구 라이선스 페이지로  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">이동한</a> 다음 요청 **탭을** 선택합니다.
2. 검토할 요청이 포함된 행을 선택합니다. 오른쪽 창에는 제품에 대한 라이선스를 원하는 사용자에 대한 세부 정보가 표시 됩니다.
3. 전체 요청을 거부하려면 승인 안 을 선택하고 대화 상자에서 승인 **안 을 선택합니다.**
4. 일부 요청을 거부하지만 다른 사용자를 승인하려면 제거할 사용자의 이름으로 X를 선택합니다. 해당 이름은 이러한 사용자에게 할당 안 에서 **이동됩니다.**
5. 두 개 이상의 제품이 있는 경우 제품 선택에서 라이선스를 할당하는 데 사용할 제품을 선택합니다.
6. 사용자가 특정 앱 및 서비스에 대한 액세스를 거부할 수 있도록 앱 및 서비스 켜기 또는 끄기 를 확장한 다음 제외할 앱에 대한 확인란의 선택을 취소합니다.
7. 창 아래쪽의 텍스트 상자에 선택적 메시지를 입력합니다.
8. 완료되면 승인 을 **선택합니다.** 오른쪽 창에는 요청의 세부 정보가 표시 됩니다.
9. 오른쪽 창을 닫습니다.
    사용자는 요청이 승인 또는 거부되었습니다.는 전자 메일을 받게 됩니다.

## <a name="related-content"></a>관련 콘텐츠

[사용자에게 라이선스 할당](../../admin/manage/assign-licenses-to-users.md)(문서)\
[사용자를 다른 구독으로](../subscriptions/move-users-different-subscription.md) 이동(문서)\
[구독 라이선스 구입 또는](buy-licenses.md) 제거(문서)
