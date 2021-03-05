---
title: 웹에서 Outlook에서 사서함을 찾을 수 없는 오류 발생
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 라이선스가 없는 사용자에게 라이선스를 추가하여 사서함을 찾을 수 없는 오류를 수정하는 방법을 배워야 합니다.
ms.openlocfilehash: e5cdb7b48f3634d51dfe1862d07d58a23e125135
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454328"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="83fcc-103">웹에서 Outlook에서 사서함을 찾을 수 없는 오류 발생</span><span class="sxs-lookup"><span data-stu-id="83fcc-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="83fcc-104">웹용 Outlook을 사용 중일 때  오류로 사서함을 찾을 수 없는 경우 웹용 Outlook에 연결하는 데 사용한 계정에 Exchange Online 라이선스가 없습니다. 따라서 사서함이 계정과 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83fcc-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> <span data-ttu-id="83fcc-105">관리자는 다음 단계에 따라 계정에 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83fcc-105">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="83fcc-106">Microsoft [365](https://portal.office.com/adminportal/home#/homepage) 관리 센터를  열고 사용자  섹션에서 활성 사용자로 이동한 다음 오류가 표시하는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83fcc-106">Open the  [Microsoft 365 admin center](https://portal.office.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
2. <span data-ttu-id="83fcc-107">열 수 있는 사용자 페이지에서 라이선스  및 앱 섹션으로 이동하여 적절한 위치 값을 선택한 다음 Exchange Online이 포함된 라이선스를 할당합니다(라이선스를 확장하여 세부 정보를 확인). </span><span class="sxs-lookup"><span data-stu-id="83fcc-107">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> <span data-ttu-id="83fcc-108">완료되면 변경 내용 저장 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="83fcc-108">When you're finished, click  **Save changes**.</span></span>
