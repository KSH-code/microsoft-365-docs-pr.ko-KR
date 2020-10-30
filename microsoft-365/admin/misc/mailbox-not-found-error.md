---
title: 웹용 Outlook에서 사서함을 찾을 수 없음 오류 발생
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 사용 되지 않는 사용자에 게 라이선스를 추가 하 여 사서함을 찾을 수 없다는 오류를 해결 하는 방법을 알아봅니다.
ms.openlocfilehash: bf8ff57704b97c8ef278938675113f5de11849de
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804889"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="7afb8-103">웹용 Outlook에서 사서함을 찾을 수 없음 오류가 발생 했습니까?</span><span class="sxs-lookup"><span data-stu-id="7afb8-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="7afb8-104">웹에서 Outlook을 사용 하는 경우 오류  **에 대해 사서함을 찾을 수**  없는 경우에는 웹에서 outlook에 연결 하는 데 사용한 계정에 Exchange Online 라이선스가 없으며, 따라서 해당 계정과 연결 된 사서함이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7afb8-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> <span data-ttu-id="7afb8-105">관리자는 다음 단계를 수행 하 여 사용자 계정에 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7afb8-105">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="7afb8-106">[Microsoft 365 관리 센터](https://portal.office.com/adminportal/home#/homepage) 를 열고 **사용자** 섹션 아래의 **활성 사용자** 로 이동한 다음 오류가 발생 한 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afb8-106">Open the  [Microsoft 365 admin center](https://portal.office.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
2. <span data-ttu-id="7afb8-107">열리는 사용자 페이지에서  **라이선스 및 앱**  섹션으로 이동 하 고, 적절 한  **위치**  값을 선택 하 고, Exchange Online이 포함 된 라이선스를 할당 합니다 (해당 세부 정보를 보려면 라이선스 확장).</span><span class="sxs-lookup"><span data-stu-id="7afb8-107">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> <span data-ttu-id="7afb8-108">작업이 완료 되 면  **변경 내용 저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7afb8-108">When you're finished, click  **Save changes** .</span></span>
