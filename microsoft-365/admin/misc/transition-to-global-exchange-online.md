---
title: MX 레코드를 업데이트하여 전역 Exchange Online 서비스로 전환
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 클라우드 독일 클라우드에서 글로벌 Exchange Online 서비스로 전환하는 Exchange Online 방법 학습
ms.openlocfilehash: 8de64e30205b07a0c20a8ae4f7cdedbf6cc6824f
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644858"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="61e40-103">MX 레코드를 업데이트하여 전역 Exchange Online 서비스로 전환</span><span class="sxs-lookup"><span data-stu-id="61e40-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="61e40-104">Microsoft 365 [포털에 로그인하고](https://admin.microsoft.com)도메인 설정   >  **이동**</span><span class="sxs-lookup"><span data-stu-id="61e40-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="61e40-105">각 도메인의 오른쪽에 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e40-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="61e40-106">조직의 도메인이 Microsoft 클라우드 독일을 Exchange Online MX 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e40-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="61e40-107">도메인을 클릭한 다음 검색된 DNS 오류를 **클릭하고 여기를 클릭하여 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="61e40-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="61e40-108">이 페이지에는 MX 레코드를 수정하는 방법을 설명하는 지침이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61e40-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="61e40-109">도메인의 등록 기관에서 Domain 커넥트 를 사용하는 경우 맨 위에 있는 "내 레코드 [수정"을](../setup/add-domain.md#registrars-with-domain-connect)클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e40-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="61e40-110">그렇지 않으면 마법사의 링크를 따라 등록 기관에 대한 단계별 지침을 **따를** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e40-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>