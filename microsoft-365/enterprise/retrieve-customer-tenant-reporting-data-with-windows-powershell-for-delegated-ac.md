---
title: DAP 파트너에 대한 사용자 지정을 사용하여 Windows PowerShell 보고 데이터 검색
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: '요약: Microsoft Exchange Online용 원격Windows PowerShell을 사용하여 개별 고객 테넌트에서 보고서를 검색합니다.'
ms.openlocfilehash: 8a244e1178e64d27d5e0f061d094dccd39bb8275
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290078"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="8a73c-103">DAP(위임된 액세스 권한) 파트너용 Windows PowerShell을 사용하여 고객 테넌트 보고 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="8a73c-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="8a73c-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="8a73c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8a73c-105">원격 Windows PowerShell 사용하여 Microsoft Exchange Online 테넌트에서 보고서를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a73c-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>

<span data-ttu-id="8a73c-106">Syndication 및 클라우드 솔루션 공급자(CSP) 파트너는 PowerShell용 원격 서비스를 통해 직접 고객 테넌트 보고서를 Windows PowerShell 데이터에 액세스할 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a73c-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="8a73c-107">이를 통해 파트너는 보고 데이터를 수집하고 저장한 후 여기에서 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a73c-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="8a73c-108">원격 연결을 연 후 고객 테넌트에 대한 보고 데이터 검색은 고객 테넌트에 대해 cmdlet을 실행하는 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8a73c-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>

<span data-ttu-id="8a73c-109">이 문서에서는 원격 Windows PowerShell 사용하여 Exchange Online 테넌트에 연결하고 보고서를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8a73c-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="8a73c-110">기본적으로 Windows PowerShell 테넌트의 보고 데이터 집계를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a73c-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="8a73c-111">이 절차를 사용하여 검색하는 보고서는 연결하는  _DelegatedOrg에만_ 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8a73c-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8a73c-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="8a73c-112">Before you begin</span></span>

- <span data-ttu-id="8a73c-p103">원격 Windows PowerShell을 사용하여 Exchange Online 테넌트에 연결해야 합니다. 자세한 내용은 [DAP(위임된 액세스 권한) 파트너용 원격 Windows PowerShell을 사용하여 Exchange Online 테넌트에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a73c-p103">You need to connect to your Exchange Online tenant by using remote Windows PowerShell. For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](/powershell/exchange/connect-to-exchange-online-powershell)</span></span>

## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="8a73c-115">Get-StaleMailboxReport 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="8a73c-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="8a73c-116">원격 세션을 Exchange Online으로 연 후 이 명령을 실행하여 날짜 범위 2015/03/25에서 2015/03/31까지에 대해 **Get-StaleMailboxReport** 를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8a73c-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="8a73c-p104">사용할 수 있는 메시지 추적에 대해 Exchange Online, Lync Online, SharePoint Online 등에 다양한 보고 cmdlet을 사용할 수 있습니다. 사용 가능한 보고 cmdlet 및 Office 365 보고 웹 서비스에 대한 자세한 내용은 다음 섹션의 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a73c-p104">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use. To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a73c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a73c-119">See also</span></span>

<span data-ttu-id="8a73c-120">[Office 365 보고 웹 서비스](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="8a73c-120">[Office 365 Reporting web service](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span></span>

[<span data-ttu-id="8a73c-121">Exchange Online의 보고 cmdlet</span><span class="sxs-lookup"><span data-stu-id="8a73c-121">Reporting cmdlets in Exchange Online</span></span>](/powershell/module/exchange/get-csclientdevicedetailreport)

[<span data-ttu-id="8a73c-122">파트너를 위한 도움말</span><span class="sxs-lookup"><span data-stu-id="8a73c-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)
