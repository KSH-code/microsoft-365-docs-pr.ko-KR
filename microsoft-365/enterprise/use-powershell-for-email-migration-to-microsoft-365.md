---
title: 전자 메일용 PowerShell을 사용하여 Office 365로 마이그레이션
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 795158e1-7dfc-4d9e-b805-373dd576c4e7
description: 이 문서에서는 PowerShell을 사용 하 여 기존 시스템에서 Microsoft 365으로 전자 메일을 마이그레이션하는 방법을 알아봅니다.
ms.openlocfilehash: afbed872c3cac483c63e8a2d537931220c3c349c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692890"
---
# <a name="use-powershell-for-email-migration-to-microsoft-365"></a><span data-ttu-id="7a793-103">전자 메일용 PowerShell을 사용하여 Office 365로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7a793-103">Use PowerShell for email migration to Microsoft 365</span></span>

<span data-ttu-id="7a793-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7a793-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7a793-105">관리자가 Microsoft 365를 처음 설정 하면 대부분의 사용자는 기존 시스템에서 전자 메일을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="7a793-105">When administrators first set up Microsoft 365, many of them migrate email from existing systems.</span></span> <span data-ttu-id="7a793-106">Microsoft 365 관리 센터를 사용 하 여이 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a793-106">You can also do this by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="7a793-107">Windows PowerShell을 사용하여 전자 메일을 마이그레이션할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a793-107">You can also use Windows PowerShell to migrate email.</span></span>
  
<span data-ttu-id="7a793-108">Windows PowerShell을 사용 하 여 Microsoft 365로 전자 메일을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="7a793-108">Use Windows PowerShell to migrate email to Microsoft 365.</span></span> 
  
- [<span data-ttu-id="7a793-109">PowerShell을 사용하여 Microsoft 365로 컷오버 마이그레이션 수행</span><span class="sxs-lookup"><span data-stu-id="7a793-109">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md)
    
- [<span data-ttu-id="7a793-110">PowerShell을 사용하여 Microsoft 365로 IMAP 마이그레이션 수행</span><span class="sxs-lookup"><span data-stu-id="7a793-110">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>](use-powershell-to-perform-an-imap-migration-to-microsoft-365.md)
    
- [<span data-ttu-id="7a793-111">PowerShell을 사용하여 Microsoft 365로 미리 구성된 마이그레이션 수행</span><span class="sxs-lookup"><span data-stu-id="7a793-111">Use PowerShell to perform a staged migration to Microsoft 365</span></span>](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md)
    
## <a name="related-topics"></a><span data-ttu-id="7a793-112">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7a793-112">Related topics</span></span>

[<span data-ttu-id="7a793-113">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="7a793-113">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7a793-114">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="7a793-114">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7a793-115">PowerShell로 SharePoint 온라인 관리</span><span class="sxs-lookup"><span data-stu-id="7a793-115">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
<span data-ttu-id="7a793-116">[Windows PowerShell을 사용 하 여 Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md) 
 에서 보고서 만들기 [Microsoft 365 PowerShell을 사용 해야 하는 이유](why-you-need-to-use-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="7a793-116">[Use Windows PowerShell to create reports in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)
[Why you need to use Microsoft 365 PowerShell](why-you-need-to-use-microsoft-365-powershell.md)</span></span>
  
[<span data-ttu-id="7a793-117">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="7a793-117">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

