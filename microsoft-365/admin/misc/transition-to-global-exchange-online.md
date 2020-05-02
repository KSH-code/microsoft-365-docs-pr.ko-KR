---
title: 전역 Exchange Online 서비스로 전환 되도록 MX 레코드 업데이트
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft Cloud 전라남도 Exchange Online에서 전역 Exchange Online 서비스로 전환 하는 방법을 알아봅니다.
ms.openlocfilehash: 276a12095cbad5b9bcaf1c48fe5d26ee20232e54
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003021"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="0ac8e-103">전역 Exchange Online 서비스로 전환 되도록 MX 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="0ac8e-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="0ac8e-104">[Microsoft 365 관리 포털](https://admin.microsoft.com)에 로그인 하 고 **설정** > **도메인** 으로 이동</span><span class="sxs-lookup"><span data-stu-id="0ac8e-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="0ac8e-105">각 도메인의 오른쪽에 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="0ac8e-106">조직의 도메인이 Microsoft Cloud 전라남도 Exchange Online을 가리킬 경우 MX 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="0ac8e-107">도메인을 클릭 **하 고 검색 된 DNS 오류를 클릭 한 다음 확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="0ac8e-108">이 페이지에는 MX 레코드를 수정 하는 방법을 보여 주는 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="0ac8e-109">도메인 등록 기관에서 [도메인 연결](../setup/add-domain.md#registrars-with-domain-connect)을 사용 하는 경우 맨 위에서 "내 레코드 수정"을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="0ac8e-110">그렇지 않으면 마법사의 링크를 따라 등록자에 대 한 단계별 **지침** 을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>