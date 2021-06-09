---
title: Office 365 GCC High용 DNS 레코드
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: '요약: 높은 Office 365 GCC DNS 레코드'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692492"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="c89a0-103">Office 365 GCC High용 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="c89a0-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="c89a0-104">*이 문서는 High 및 Office 365 GCC 높음 Microsoft 365 GCC 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="c89a0-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="c89a0-105">High를 등록하는 Office 365 GCC 온라인 서비스 테넌트에 SMTP 및 SIP 도메인을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89a0-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="c89a0-106">Azure AD PowerShell의 New-MsolDomain cmdlet을 사용하여 이 작업을 진행하거나 [Azure Government Portal을](https://portal.azure.us) 사용하여 도메인 추가 및 소유권 확인 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c89a0-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="c89a0-107">테넌트에 도메인을 추가하고 유효성을 검사한 후 다음 지침을 사용하여 서비스에 적합한 DNS 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c89a0-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="c89a0-108">인바운드 MX 레코드 및 기존 자동 Exchange 조직 요구에 맞게 아래 표를 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c89a0-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="c89a0-109">이러한 DNS 레코드를 메시징 팀과 조정하여 전자 메일이 잘못 배달되지 않도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c89a0-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="c89a0-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c89a0-110">Exchange Online</span></span>

| <span data-ttu-id="c89a0-111">종류</span><span class="sxs-lookup"><span data-stu-id="c89a0-111">Type</span></span> | <span data-ttu-id="c89a0-112">우선 순위</span><span class="sxs-lookup"><span data-stu-id="c89a0-112">Priority</span></span> | <span data-ttu-id="c89a0-113">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="c89a0-113">Host name</span></span> | <span data-ttu-id="c89a0-114">주소 또는 값을 가리킴</span><span class="sxs-lookup"><span data-stu-id="c89a0-114">Points to address or value</span></span> | <span data-ttu-id="c89a0-115">TTL</span><span class="sxs-lookup"><span data-stu-id="c89a0-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="c89a0-116">MX</span><span class="sxs-lookup"><span data-stu-id="c89a0-116">MX</span></span> | <span data-ttu-id="c89a0-117">0</span><span class="sxs-lookup"><span data-stu-id="c89a0-117">0</span></span> | @ | <span data-ttu-id="c89a0-118">*tenant*.mail.protection.office365.us(자세한 내용은 아래 참조)</span><span class="sxs-lookup"><span data-stu-id="c89a0-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="c89a0-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c89a0-119">1 Hour</span></span> |
| <span data-ttu-id="c89a0-120">TXT</span><span class="sxs-lookup"><span data-stu-id="c89a0-120">TXT</span></span> | - | @ | <span data-ttu-id="c89a0-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="c89a0-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="c89a0-122">1시간</span><span class="sxs-lookup"><span data-stu-id="c89a0-122">1 Hour</span></span> |
| <span data-ttu-id="c89a0-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="c89a0-123">CNAME</span></span> | - | <span data-ttu-id="c89a0-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c89a0-124">autodiscover</span></span> | <span data-ttu-id="c89a0-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="c89a0-125">autodiscover.office365.us</span></span> | <span data-ttu-id="c89a0-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c89a0-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="c89a0-127">Exchange Autodiscover 레코드</span><span class="sxs-lookup"><span data-stu-id="c89a0-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="c89a0-128">모든 Exchange Server 있는 경우 마이그레이션할 때 기존 레코드를 현재 Exchange Online 레코드를 업데이트하고 마이그레이션을 완료한 후 해당 레코드를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c89a0-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="c89a0-129">Exchange Online MX 레코드</span><span class="sxs-lookup"><span data-stu-id="c89a0-129">Exchange Online MX Record</span></span>

<span data-ttu-id="c89a0-130">허용 도메인의 MX 레코드 값은 위에서 언급한 표준 형식(테넌트 .mail.protection.office365.us)을  따르며, 테넌트는 기본 테넌트 이름의 첫 번째 부분으로 바됩니다. </span><span class="sxs-lookup"><span data-stu-id="c89a0-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="c89a0-131">예를 들어 테넌트 이름이 contoso.onmicrosoft.us MX 레코드의  값으로 contoso.mail.protection.office365.us 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c89a0-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="c89a0-132">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="c89a0-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="c89a0-133">CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="c89a0-133">CNAME records</span></span>

| <span data-ttu-id="c89a0-134">유형</span><span class="sxs-lookup"><span data-stu-id="c89a0-134">Type</span></span> | <span data-ttu-id="c89a0-135">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="c89a0-135">Host name</span></span> | <span data-ttu-id="c89a0-136">주소 또는 값을 가리킴</span><span class="sxs-lookup"><span data-stu-id="c89a0-136">Points to address or value</span></span> | <span data-ttu-id="c89a0-137">TTL</span><span class="sxs-lookup"><span data-stu-id="c89a0-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="c89a0-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="c89a0-138">CNAME</span></span> | <span data-ttu-id="c89a0-139">sip</span><span class="sxs-lookup"><span data-stu-id="c89a0-139">sip</span></span> | <span data-ttu-id="c89a0-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="c89a0-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="c89a0-141">1시간</span><span class="sxs-lookup"><span data-stu-id="c89a0-141">1 Hour</span></span> |
| <span data-ttu-id="c89a0-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="c89a0-142">CNAME</span></span> | <span data-ttu-id="c89a0-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c89a0-143">lyncdiscover</span></span> | <span data-ttu-id="c89a0-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="c89a0-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="c89a0-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c89a0-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="c89a0-146">SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="c89a0-146">SRV records</span></span>

| <span data-ttu-id="c89a0-147">유형</span><span class="sxs-lookup"><span data-stu-id="c89a0-147">Type</span></span> | <span data-ttu-id="c89a0-148">서비스</span><span class="sxs-lookup"><span data-stu-id="c89a0-148">Service</span></span> | <span data-ttu-id="c89a0-149">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="c89a0-149">Protocol</span></span> | <span data-ttu-id="c89a0-150">포트</span><span class="sxs-lookup"><span data-stu-id="c89a0-150">Port</span></span> | <span data-ttu-id="c89a0-151">가중치</span><span class="sxs-lookup"><span data-stu-id="c89a0-151">Weight</span></span> | <span data-ttu-id="c89a0-152">우선 순위</span><span class="sxs-lookup"><span data-stu-id="c89a0-152">Priority</span></span> | <span data-ttu-id="c89a0-153">이름</span><span class="sxs-lookup"><span data-stu-id="c89a0-153">Name</span></span> | <span data-ttu-id="c89a0-154">대상</span><span class="sxs-lookup"><span data-stu-id="c89a0-154">Target</span></span> | <span data-ttu-id="c89a0-155">TTL</span><span class="sxs-lookup"><span data-stu-id="c89a0-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="c89a0-156">SRV</span><span class="sxs-lookup"><span data-stu-id="c89a0-156">SRV</span></span> | <span data-ttu-id="c89a0-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="c89a0-157">\_sip</span></span> | <span data-ttu-id="c89a0-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="c89a0-158">\_tls</span></span> | <span data-ttu-id="c89a0-159">443</span><span class="sxs-lookup"><span data-stu-id="c89a0-159">443</span></span> | <span data-ttu-id="c89a0-160">1</span><span class="sxs-lookup"><span data-stu-id="c89a0-160">1</span></span> | <span data-ttu-id="c89a0-161">100</span><span class="sxs-lookup"><span data-stu-id="c89a0-161">100</span></span> | @ | <span data-ttu-id="c89a0-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="c89a0-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="c89a0-163">1시간</span><span class="sxs-lookup"><span data-stu-id="c89a0-163">1 Hour</span></span> |
| <span data-ttu-id="c89a0-164">SRV</span><span class="sxs-lookup"><span data-stu-id="c89a0-164">SRV</span></span> | <span data-ttu-id="c89a0-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c89a0-165">\_sipfederationtls</span></span> | <span data-ttu-id="c89a0-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="c89a0-166">\_tcp</span></span> | <span data-ttu-id="c89a0-167">5061</span><span class="sxs-lookup"><span data-stu-id="c89a0-167">5061</span></span> | <span data-ttu-id="c89a0-168">1</span><span class="sxs-lookup"><span data-stu-id="c89a0-168">1</span></span> | <span data-ttu-id="c89a0-169">100</span><span class="sxs-lookup"><span data-stu-id="c89a0-169">100</span></span> | @ | <span data-ttu-id="c89a0-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="c89a0-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="c89a0-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c89a0-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="c89a0-172">추가 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="c89a0-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c89a0-173">DNS 영역의 기존 *msoid* CNAME 레코드가 있는  경우 지금 DNS에서 레코드를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89a0-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="c89a0-174">msoid 레코드는 Microsoft 365 Enterprise 앱(이전의 앱)과 Office 365 ProPlus *정품* 인증이 성공하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c89a0-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
