---
title: PowerShell로 Microsoft 365 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- O365ITProTrain
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 932d57c0-1520-4f0f-8ec9-9966d646480f
description: PowerShell을 사용하여 Microsoft 365, 라이선스 및 365 앱을 관리하는 방법을 학습합니다.
ms.openlocfilehash: dee8fbce03e38a954ddea5a8ec86248f9209d96c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905107"
---
# <a name="manage-microsoft-365-with-powershell"></a><span data-ttu-id="b17f2-103">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="b17f2-103">Manage Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="b17f2-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="b17f2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b17f2-105">Microsoft 365 PowerShell은 Microsoft 365 관리 센터를 보완하는 강력한 관리 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b17f2-105">PowerShell for Microsoft 365 is a powerful management tool that complements the Microsoft 365 admin center.</span></span> <span data-ttu-id="b17f2-106">예를 들어 PowerShell 자동화를 사용하여 여러 사용자 계정 및 라이선스를 쉽게 관리하고 보고서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17f2-106">For example, you can use PowerShell automation to easily manage multiple user accounts and licenses and to create reports.</span></span>

<span data-ttu-id="b17f2-107">다음 항목에서 PowerShell을 사용하여 PowerShell을 관리하는 방법을 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b17f2-107">Select from the following topics to learn how to use PowerShell to manage Microsoft 365:</span></span>
  
- [<span data-ttu-id="b17f2-108">**시작하기**</span><span class="sxs-lookup"><span data-stu-id="b17f2-108">**Get started**</span></span>](getting-started-with-microsoft-365-powershell.md)

    <span data-ttu-id="b17f2-109">Microsoft 365 PowerShell에 익숙하지 않은 경우 여기에서 시작하고 Microsoft 365 모듈을 설치하고 구독에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b17f2-109">Start here if you're not familiar with PowerShell for Microsoft 365, and you want to install the Microsoft 365 modules and connect to your subscription.</span></span>

- [<span data-ttu-id="b17f2-110">**사용자 계정, 라이선스 및 그룹**</span><span class="sxs-lookup"><span data-stu-id="b17f2-110">**User accounts, licenses, and groups**</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

    <span data-ttu-id="b17f2-111">자동화 명령을 사용하여 사용자 계정, 라이선스 및 그룹을 관리하는 방법을 알아보고 싶은 경우 여기에서 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="b17f2-111">Start here if want to learn about using automation commands to manage user accounts, licenses, and groups.</span></span>

- [<span data-ttu-id="b17f2-112">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="b17f2-112">**SharePoint**</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)

    <span data-ttu-id="b17f2-113">자동화 명령을 사용하여 자동화 기능을 관리하려는 경우 여기에서 SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b17f2-113">Start here if you want to use automation commands to manage SharePoint.</span></span>

- [<span data-ttu-id="b17f2-114">**Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="b17f2-114">**Exchange Online**</span></span>](/powershell/exchange/exchange-online-powershell)

    <span data-ttu-id="b17f2-115">사용자 계정 관리에 필요한 경우 여기에서 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b17f2-115">Start here if you want to manage Exchange Online.</span></span>

- [<span data-ttu-id="b17f2-116">**전자 메일 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="b17f2-116">**Email migration**</span></span>](use-powershell-for-email-migration-to-microsoft-365.md)

    <span data-ttu-id="b17f2-117">기존 시스템에서 전자 메일을 마이그레이션하려면 여기에서 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="b17f2-117">Start here if you want to migrate your email from pre-existing systems.</span></span>

- [<span data-ttu-id="b17f2-118">**보안 및 준수 센터**</span><span class="sxs-lookup"><span data-stu-id="b17f2-118">**Security & Compliance Center**</span></span>](/powershell/exchange/scc-powershell)

    <span data-ttu-id="b17f2-119">보안 및 준수 센터 기능을 관리하려는 경우 & 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="b17f2-119">Start here if you want to manage Security & Compliance Center features.</span></span>

- [<span data-ttu-id="b17f2-120">**DAP(위임된 액세스 권한) 파트너**</span><span class="sxs-lookup"><span data-stu-id="b17f2-120">**Delegated Access Permissions (DAP) partners**</span></span>](manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-dap-p.md)

    <span data-ttu-id="b17f2-121">Syndication 및 CSP(클라우드 솔루션 공급자) 파트너를 사용하여 고객 테넌트의 Microsoft 365 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="b17f2-121">Start here if you want to use Syndication and Cloud Solution Provider (CSP) partners to manage your Microsoft 365 customer tenants.</span></span>

- [<span data-ttu-id="b17f2-122">**비즈니스용 Skype 온라인**</span><span class="sxs-lookup"><span data-stu-id="b17f2-122">**Skype for Business Online**</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)

    <span data-ttu-id="b17f2-123">여기에서 시작하여 온라인 비즈니스용 Skype 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b17f2-123">Start here to manage Skype for Business Online.</span></span>