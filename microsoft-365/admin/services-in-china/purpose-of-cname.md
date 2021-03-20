---
title: MSOID용 Office 365 CNAME 레코드의 용도
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 인증 프로세스에 가장 적합한 서버로 연결되는 Office 365의 'MSOID' CNAME 레코드에 대해 자세히 알아보면 응답 속도가 빨라집니다.
monikerRange: o365-21vianet
ms.openlocfilehash: a1d587abc9db03c9a1f7c5f66711fde3648a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914309"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="18c2e-103">MSOID용 Office 365 CNAME 레코드의 용도</span><span class="sxs-lookup"><span data-stu-id="18c2e-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="18c2e-104">원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요.</span><span class="sxs-lookup"><span data-stu-id="18c2e-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="18c2e-105">다음은 21Vianet에서 운영하는 \*\*Office 365에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c2e-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="18c2e-p101">Office 365에서 "MSOID" CNAME 레코드를 추가해야 하는 이유가 궁금할 수 있습니다. 이 레코드는 사용하는 구독에 상관없이 모든 사용자 지정 도메인에 대해 추가해야 하는 레코드입니다. CNAME 레코드가 필요한 이유는 무엇인가요? 약간 기술적이지만 필수적인 요소로, 특정 인증 프로세스를 위해 최상의 서버로 연결시켜 주기 때문에 보다 빠르게 응답을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18c2e-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="18c2e-p102">기술 세부 사항: 비즈니스용 Skype Online, Outlook, Windows PowerShell 또는 Microsoft Azure Active Directory 동기화 도구 등 Office 365와 연동되는 클라이언트 응용 프로그램을 실행하는 경우 자격 증명이 인증되어 있어야 합니다. Office 365는 CNAME 레코드를 사용하여 사용자 위치의 정확한 인증 끝점을 가리키므로 빠른 인증 응답 시간이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="18c2e-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="18c2e-p103">CNAME 레코드가 도메인에서 누락된 경우 이 응용 프로그램은 미국에 있는 기본 인증 끝점을 사용하며, 이에 따라 인증 속도가 느릴 수 있습니다. **대상 주소** 에 오타가 있는 경우와 같이 이 CNAME 레코드가 적절하게 구성되지 않은 경우, 이 응용 프로그램은 인증할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18c2e-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="18c2e-114">**Office 365에서 도메인의 DNS** 레코드를 관리하는 경우 Office 365는 이 CNAME 레코드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="18c2e-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="18c2e-115">**DNS 호스트에서** 도메인의 DNS 레코드를 관리하는 경우 DNS 호스트의 지침에 따라 이 레코드를 [직접 만들 수 있습니다.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="18c2e-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
<span data-ttu-id="18c2e-116">Office 365 배포를 계획하고 있으며 추가 또는 업데이트해야 할 수 있는 모든 DNS 레코드에 대해 자세히 알아보고 싶은 경우 [참조: Office 365용 외부](../../enterprise/external-domain-name-system-records.md)도메인 이름 시스템 레코드에서 해당 레코드에 대해 읽어보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c2e-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](../../enterprise/external-domain-name-system-records.md).</span></span>
