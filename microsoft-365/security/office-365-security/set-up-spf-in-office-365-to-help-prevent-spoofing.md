---
title: 스푸핑을 방지할 수 있도록 SPF 설정
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365에서 사용자 지정 도메인과 함께 SPF(Sender Policy Framework)를 사용할 수 있도록 DNS(도메인 이름 서비스) 레코드를 업데이트하는 방법을 알아봅니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d200c4cf17a3d42ddafca301fecbf18c249ac37
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245687"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="19b09-103">스푸핑을 방지할 수 있도록 SPF 설정</span><span class="sxs-lookup"><span data-stu-id="19b09-103">Set up SPF to help prevent spoofing</span></span>

- [<span data-ttu-id="19b09-104">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="19b09-104">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="19b09-105">SPF TXT 레코드 생성 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="19b09-105">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
- [<span data-ttu-id="19b09-106">하위 도메인을 어떻게 처리하나요?</span><span class="sxs-lookup"><span data-stu-id="19b09-106">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="19b09-107">SPF 문제 해결</span><span class="sxs-lookup"><span data-stu-id="19b09-107">Troubleshooting SPF</span></span>](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

<span data-ttu-id="19b09-108">이 문서에서는 Office 365에서 사용자 지정 도메인과 함께 SPF(Sender Policy Framework) 전자 메일 인증을 사용할 수 있도록 DNS(Domain Name Service) 레코드를 업데이트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-108">This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="19b09-109">SPF는 사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 *유효성을 검사* 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-109">SPF helps *validate* outbound email sent from your custom domain (is coming from who it says it is).</span></span> <span data-ttu-id="19b09-110">SPF, [DKIM](use-dkim-to-validate-outbound-email.md) 및 [DMARC](use-dmarc-to-validate-email.md)의 전체 권장 전자 메일 인증 방법을 설정하는 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-110">It's a first step in setting up the full recommended email authentication methods of SPF, [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19b09-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="19b09-111">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19b09-112">**중소 기업** 이거나 IP 주소 또는 DNS 구성에 익숙하지 않은 경우 인터넷 도메인 등록 기관에 문의하여(예:</span><span class="sxs-lookup"><span data-stu-id="19b09-112">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="19b09-113">GoDaddy, Bluehost, web.com) 및 *SPF(및 기타 전자 메일 인증 방법)의 DNS 구성* 에 대한 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="19b09-113">GoDaddy, Bluehost, web.com) & ask for help with *DNS configuration of SPF* (and any other email authentication method).</span></span> <p> <span data-ttu-id="19b09-114">**사용자 지정 URL을 사용하지 않는 경우**(Office 365에 사용되는 URL은 **onmicrosoft.com** 으로 끝남) Office 365 서비스에서 SPF가 이미 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-114">**If you don't use a custom URL** (and the URL used for Office 365 ends in **onmicrosoft.com**), SPF has already been set up for you in the Office 365 service.</span></span>

<span data-ttu-id="19b09-115">지금부터 시작하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-115">Let's get started.</span></span>

<span data-ttu-id="19b09-116">Office 365용 SPF TXT 레코드는 모든 사용자 지정 도메인 또는 하위 도메인의 외부 DNS에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-116">The SPF TXT record for Office 365 will be made in external DNS for any custom domains or subdomains.</span></span> <span data-ttu-id="19b09-117">레코드를 만들 때 몇 가지 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-117">You need some information to make the record.</span></span> <span data-ttu-id="19b09-118">다음 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-118">Gather this information:</span></span>

- <span data-ttu-id="19b09-119">사용자 지정 도메인의 SPF TXT 레코드(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="19b09-119">The SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="19b09-120">지침은 [Office 365 DNS 레코드를 만드는 데 필요한 정보 수집](../../admin/get-help-with-domains/information-for-dns-records.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19b09-120">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="19b09-121">메시징 서버로 이동하여 외부 IP 주소(모든 온-프레미스 메시징 서버에서 필요)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-121">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="19b09-122">예를 들어, **131.107.2.200**.</span><span class="sxs-lookup"><span data-stu-id="19b09-122">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="19b09-123">SPF TXT 레코드에 포함해야하는 모든 제3자 도메인에 사용할 도메인 이름.</span><span class="sxs-lookup"><span data-stu-id="19b09-123">Domain names to use for all third-party domains that you need to include in your SPF TXT record.</span></span> <span data-ttu-id="19b09-124">일부 대량 메일 공급자는 고객에게 사용할 하위 도메인을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-124">Some bulk mail providers have set up subdomains to use for their customers.</span></span> <span data-ttu-id="19b09-125">예를 들어, MailChimp 회사는 **servers.mcsv.net** 을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-125">For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="19b09-126">SPF TXT 레코드에 사용할 시행 규칙을 정합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-126">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="19b09-127">**-all** 규칙이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-127">The **-all** rule is recommended.</span></span> <span data-ttu-id="19b09-128">다른 구문 옵션에 대한 자세한 내용은 [Office 365용 SPF TXT 레코드 구문](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19b09-128">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19b09-129">사용자 지정 도메인을 사용하려면 Office 365에서는 스푸핑을 방지하는 데 도움이 되도록 SPF (Sender Policy Framework) TXT 레코드를 사용자 DNS 레코드에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-129">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="19b09-130">SPF TXT 레코드 생성 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="19b09-130">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="19b09-131">다음 표에서는 SPF 구문을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-131">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="19b09-132">요소</span><span class="sxs-lookup"><span data-stu-id="19b09-132">Element</span></span>|<span data-ttu-id="19b09-133">만약 다음을 사용 중이라면...</span><span class="sxs-lookup"><span data-stu-id="19b09-133">If you're using...</span></span>|<span data-ttu-id="19b09-134">고객에게 일반적인가요?</span><span class="sxs-lookup"><span data-stu-id="19b09-134">Common for customers?</span></span>|<span data-ttu-id="19b09-135">이 항목을 추가하세요...</span><span class="sxs-lookup"><span data-stu-id="19b09-135">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="19b09-136">1</span><span class="sxs-lookup"><span data-stu-id="19b09-136">1</span></span>|<span data-ttu-id="19b09-137">모든 전자 메일 시스템 (필수)</span><span class="sxs-lookup"><span data-stu-id="19b09-137">Any email system (required)</span></span>|<span data-ttu-id="19b09-p108">일반적. 이 값으로 시작하는 모든 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="19b09-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="19b09-140">2</span><span class="sxs-lookup"><span data-stu-id="19b09-140">2</span></span>|<span data-ttu-id="19b09-141">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="19b09-141">Exchange Online</span></span>|<span data-ttu-id="19b09-142">공통</span><span class="sxs-lookup"><span data-stu-id="19b09-142">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="19b09-143">3</span><span class="sxs-lookup"><span data-stu-id="19b09-143">3</span></span>|<span data-ttu-id="19b09-144">Exchange Online 전용</span><span class="sxs-lookup"><span data-stu-id="19b09-144">Exchange Online dedicated only</span></span>|<span data-ttu-id="19b09-145">공통이 아님</span><span class="sxs-lookup"><span data-stu-id="19b09-145">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="19b09-146">4</span><span class="sxs-lookup"><span data-stu-id="19b09-146">4</span></span>|<span data-ttu-id="19b09-147">Office 365 독일, Microsoft Cloud 독일 전용</span><span class="sxs-lookup"><span data-stu-id="19b09-147">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="19b09-148">공통이 아님</span><span class="sxs-lookup"><span data-stu-id="19b09-148">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="19b09-149">5</span><span class="sxs-lookup"><span data-stu-id="19b09-149">5</span></span>|<span data-ttu-id="19b09-150">제3자 전자 메일 시스템</span><span class="sxs-lookup"><span data-stu-id="19b09-150">Third-party email system</span></span>|<span data-ttu-id="19b09-151">공통이 아님</span><span class="sxs-lookup"><span data-stu-id="19b09-151">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="19b09-152">\<domain_name\>은(는) 타사 전자 메일 시스템 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-152">\<domain_name\> is the domain of the third-party email system.</span></span>|
   |<span data-ttu-id="19b09-153">6</span><span class="sxs-lookup"><span data-stu-id="19b09-153">6</span></span>|<span data-ttu-id="19b09-p109">온-프레미스 이메일 시스템. 예를 들어 Exchange Online Protection 및 다른 메일 시스템</span><span class="sxs-lookup"><span data-stu-id="19b09-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="19b09-156">공통이 아님</span><span class="sxs-lookup"><span data-stu-id="19b09-156">Not common</span></span>|<span data-ttu-id="19b09-157">추가 메일 시스템마다 다음 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-157">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="19b09-158">\<IP_address\> 및 \<domain_name\>은(는) 도메인을 대신하여 메일을 보내는 다른 전자 메일 시스템의 IP 주소 및 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-158">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="19b09-159">7</span><span class="sxs-lookup"><span data-stu-id="19b09-159">7</span></span>|<span data-ttu-id="19b09-160">모든 전자 메일 시스템 (필수)</span><span class="sxs-lookup"><span data-stu-id="19b09-160">Any email system (required)</span></span>|<span data-ttu-id="19b09-p110">일반적. 이 값으로 끝나는 모든 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="19b09-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="19b09-163">다음 여러 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-163">This can be one of several values.</span></span> <span data-ttu-id="19b09-164">`-all`을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-164">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="19b09-165">아직 이 작업을 수행하지 않은 경우 다음 표의 구문을 사용하여 SPF TXT 레코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-165">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="19b09-166">예를 들어, Office 365에서 완전히 호스팅되는 즉, 온-프레미스 메일 서버가 없는 경우, SPF TXT 레코드에는 1, 2 및 7행이 포함되며 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-166">For example, if you are hosted entirely in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="19b09-167">**위의 예제는 가장 일반적인 SPF TXT 레코드입니다.**</span><span class="sxs-lookup"><span data-stu-id="19b09-167">**The example above is the most common SPF TXT record**.</span></span> <span data-ttu-id="19b09-168">이 레코드는 사용자의 Microsoft 데이터 센터가 미국, 유럽 (독일 포함) 또는 다른 위치에 있는지 여부에 관계없이 모든 사람에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-168">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="19b09-169">그러나 Microsoft Cloud 독일의 일부인 Office 365 Germany를 구매한 경우 2행 대신 4행의 include 문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-169">However, if you bought Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2.</span></span> <span data-ttu-id="19b09-170">예를 들어, Office 365 Germany에서 완전히 호스팅되는 즉, 온-프레미스 메일 서버가 없는 경우, SPF TXT 레코드에는 1, 4 및 7행이 포함되며 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-170">For example, if you are hosted entirely in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="19b09-171">사용자가 이미 Office 365에 배포되어 있고 사용자 지정 도메인에 대한 SPF TXT 레코드를 설정했고 Office 365 Germany로 마이그레이션하는 경우에는 SPF TXT 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-171">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="19b09-172">이렇게 하려면 `include:spf.protection.outlook.com` 를 `include:spf.protection.outlook.de`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-172">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="19b09-173">SPF TXT 레코드를 구성한 후에는 DNS에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-173">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="19b09-174">**도메인에 대해 하나의 SPF TXT 레코드만 가질 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="19b09-174">**You can only have one SPF TXT record for a domain.**</span></span> <span data-ttu-id="19b09-175">SPF TXT 레코드가 존재하는 경우 새 레코드를 추가하는 대신 기존 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-175">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="19b09-176">[Office 365용 DNS 레코드 만들기](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)로 이동한 다음 DNS 호스트에 대한 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-176">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then select the link for your DNS host.</span></span>

4. <span data-ttu-id="19b09-177">사용자의 SPF TXT 레코드를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-177">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="19b09-178">하위 도메인을 어떻게 처리합니까?</span><span class="sxs-lookup"><span data-stu-id="19b09-178">How to handle subdomains?</span></span>

<span data-ttu-id="19b09-179">*하위 도메인은 최상위 도메인의 SPF 레코드를 상속하지 않으므로 각 하위 도메인에 대해 별도의 레코드를 만들어야 합니다*.</span><span class="sxs-lookup"><span data-stu-id="19b09-179">It's important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top-level domain*.</span></span>

<span data-ttu-id="19b09-180">모든 도메인 및 하위 도메인에 대해 와일드카드 SPF 레코드(`*.`)가 있어야 공격자가 존재하지 않는 하위 도메인에서 보낸다고 주장하는 전자 메일을 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-180">A wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="19b09-181">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="19b09-181">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="19b09-182">SPF 문제 해결</span><span class="sxs-lookup"><span data-stu-id="19b09-182">Troubleshooting SPF</span></span>

<span data-ttu-id="19b09-183">SPF TXT 레코드에 문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="19b09-183">Having trouble with your SPF TXT record?</span></span> <span data-ttu-id="19b09-184">[문제 해결: Office 365의 SPF에 대한 모범 사례](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)를 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="19b09-184">Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>


## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="19b09-185">SPF 전자 메일 인증이 실제로 하는 일은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="19b09-185">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="19b09-186">SPF는 사용자를 대신하여 메일을 보낼 수 있는 메일 서버를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-186">SPF identifies which mail servers are allowed to send mail on your behalf.</span></span> <span data-ttu-id="19b09-187">기본적으로 SPF는 DKIM, DMARC 및 Office 365에서 지원하는 기타 기술과 함께 스푸핑 및 피싱을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-187">Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing.</span></span> <span data-ttu-id="19b09-188">SPF는 사용자 지정 도메인을 대신하여 메일을 보낼 수 있는 메일 서버를 식별하기 위해 DNS에서 사용하는 TXT 레코드에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-188">SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain.</span></span> <span data-ttu-id="19b09-189">받는 사람의 메일 시스템은 SPF TXT 레코드를 참조하여 사용자 지정 도메인의 메시지가 인증된 메시징 서버에서 온 것인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-189">Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="19b09-190">예를 들어 사용자 지정 도메인 contoso.com이 Office 365를 사용한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-190">For example, let's say that your custom domain contoso.com uses Office 365.</span></span> <span data-ttu-id="19b09-191">Office 365 메시징 서버를 사용자 도메인의 정상적인 메일 서버로 나열하는 SPF TXT 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-191">You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain.</span></span> <span data-ttu-id="19b09-192">수신 메시징 서버가 joe@contoso.com으로부터 메시지를 받으면 서버는 contoso.com의 SPF TXT 레코드를 조회하여 메시지가 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-192">When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid.</span></span> <span data-ttu-id="19b09-193">수신 서버에서 SPF 레코드에 나열된 Office 365 메시징 서버 이외의 서버에서 받은 메시지를 발견하는 경우 수신 메일 서버에서 메시지를 스팸으로 거부하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-193">If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="19b09-194">또한 사용자 지정 도메인에 SPF TXT 레코드가 없는 경우 일부 수신 서버에서 메시지를 완전히 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-194">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright.</span></span> <span data-ttu-id="19b09-195">이는 수신 서버에서 메시지가 인증된 메시징 서버에서 온 것인지 확인할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-195">This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="19b09-196">사용자가 Office 365용 메일을 이미 설정한 경우 SPF TXT 레코드로 Microsoft 메시징 서버를 DNS에 이미 포함 시켰습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-196">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record.</span></span> <span data-ttu-id="19b09-197">그러나 DNS에서 SPF TXT 레코드를 업데이트해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-197">However, there are some cases where you may need to update your SPF TXT record in DNS.</span></span> <span data-ttu-id="19b09-198">예:</span><span class="sxs-lookup"><span data-stu-id="19b09-198">For example:</span></span>

- <span data-ttu-id="19b09-199">이전에는 SharePoint Online을 사용하는 경우 다른 SPF TXT 레코드를 사용자 지정 도메인에 추가해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-199">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online.</span></span> <span data-ttu-id="19b09-200">이 작업은 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-200">This is no longer required.</span></span> <span data-ttu-id="19b09-201">이렇게 변경하면 정크 메일 폴더에 SharePoint Online 알림 메시지가 표시될 위험이 줄어 듭니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-201">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="19b09-202">조회 제한 10개에 도달하여 "조회 제한 초과" 및 "너무 많은 홉"과 같은 오류가 발생하는 경우 SPF TXT 레코드를 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="19b09-202">Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="19b09-203">Office 365 및 Exchange 온-프레미스의 하이브리드 환경이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="19b09-203">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="19b09-204">DKIM 및 DMARC (권장)를 설정하려고합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-204">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="19b09-205">SPF에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="19b09-205">More information about SPF</span></span>

<span data-ttu-id="19b09-206">지원되는 SPF 구문, 스푸핑, 문제 해결 및 Office 365에서 SPF를 지원하는 방법에 대한 자세한 내용과 고급 예제를 보려면 [SPF가 Office 365에서 스푸핑 및 피싱을 방지하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19b09-206">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-dkim-and-dmarc"></a><span data-ttu-id="19b09-207">다음 단계: DKIM 및 DMARC</span><span class="sxs-lookup"><span data-stu-id="19b09-207">Next Steps: DKIM and DMARC</span></span>

 <span data-ttu-id="19b09-208">SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-208">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="19b09-209">이 같은 기술로부터 방어하려면 SPF를 설정한 후에 Office 365용 DKIM 및 DMARC를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-209">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="19b09-210">[DKIM](use-dkim-to-validate-outbound-email.md) 전자 메일 인증의 목표는 전자 메일 내용이 위조되지 않았다는 것을 증명하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-210">[DKIM](use-dkim-to-validate-outbound-email.md) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="19b09-211">[DMARC](use-dmarc-to-validate-email.md) 전자 메일 인증의 목표는 SPF 및 DKIM 정보가 보낸 주소와 일치하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19b09-211">[DMARC](use-dmarc-to-validate-email.md) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>

 <span data-ttu-id="19b09-212">지원되는 SPF 구문에 대한 자세한 내용과 고급 예제를 보려면 [SPF가 Office 365에서 스푸핑 및 피싱을 방지하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19b09-212">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="19b09-213">*이 문서에 대한 피드백이 있는 경우 '피드백' 아래에서 '이 페이지'를 선택합니다.*</span><span class="sxs-lookup"><span data-stu-id="19b09-213">*Select 'This page' under 'Feedback' if you have feedback on this documentation.*</span></span>
