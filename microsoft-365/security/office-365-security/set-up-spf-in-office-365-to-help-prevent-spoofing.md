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
ms.openlocfilehash: 0a2c400e77c83fa61e276dee1d870835d466b5af
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599550"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="1cb66-103">스푸핑을 방지할 수 있도록 SPF 설정</span><span class="sxs-lookup"><span data-stu-id="1cb66-103">Set up SPF to help prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1cb66-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="1cb66-104">**Applies to**</span></span>
- [<span data-ttu-id="1cb66-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1cb66-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1cb66-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="1cb66-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1cb66-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1cb66-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1cb66-108">이 문서에서는 Office 365에서 사용자 지정 도메인과 함께 SPF(Sender Policy Framework) 전자 메일 인증을 사용할 수 있도록 DNS(Domain Name Service) 레코드를 업데이트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-108">This article describes how to update an Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="1cb66-109">SPF를 사용하여 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="1cb66-109">Using SPF helps to validate outbound email sent from your custom domain.</span></span> <span data-ttu-id="1cb66-110">다른 권장 전자 메일 인증 방법 DMARC 및 DKIM(Office 365에서 지원되는 두 가지 추가 전자 메일 인증 방법)을 설정하는 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-110">It's a first step in setting up other recommended email authentication methods DMARC and DKIM (two further email authentication methods supported in Office 365).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1cb66-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="1cb66-111">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cb66-112">**중소 기업** 이거나 IP 주소 또는 DNS 구성에 익숙하지 않은 경우 인터넷 도메인 등록 기관에 문의하여(예:</span><span class="sxs-lookup"><span data-stu-id="1cb66-112">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="1cb66-113">GoDaddy, Bluehost, web.com) SPF(및 기타 전자 메일 인증 방법)의 DNS 구성에 대한 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="1cb66-113">GoDaddy, Bluehost, web.com) to ask for help with DNS configuration of SPF (and any other email authentication method).</span></span> <span data-ttu-id="1cb66-114">*또한* 사용자 지정 URL을 구매하지 않았거나 사용하지 않는 경우(즉, 귀하와 귀하의 고객이 Office 365에 연결하기 위해 검색하는 **onmicrosoft.com** 으로 끝나는 URL) SPF는 Office 365 서비스에 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-114">*Also*, if you haven't bought, or don't use a custom URL (in other words the URL you and your customers browse to reach Office 365 ends in **onmicrosoft.com**), SPF has been set up for you in the Office 365 service.</span></span> <span data-ttu-id="1cb66-115">이 경우 추가 단계가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-115">No further steps are required in that case.</span></span> <span data-ttu-id="1cb66-116">읽어주셔서 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-116">Thanks for reading.</span></span>

<span data-ttu-id="1cb66-117">외부 DNS에서 Office 365에 대한 SPF TXT 레코드를 생성하거나 업데이트하기 전에 레코드를 만드는 데 필요한 정보를 수집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-117">Before you create or update the SPF TXT record for Office 365 in external DNS, you need to gather some information needed to make the record.</span></span> <span data-ttu-id="1cb66-118">지원되는 SPF 구문에 대한 자세한 내용과 고급 예제를 보려면 [SPF가 Office 365에서 스푸핑 및 피싱을 방지하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cb66-118">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="1cb66-119">다음 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-119">Gather this information:</span></span>

- <span data-ttu-id="1cb66-120">사용자 정의 도메인의 현재 SPF TXT 레코드(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="1cb66-120">The current SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="1cb66-121">지침은 [Office 365 DNS 레코드를 만드는 데 필요한 정보 수집](../../admin/get-help-with-domains/information-for-dns-records.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cb66-121">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="1cb66-122">메시징 서버로 이동하여 외부 IP 주소(모든 온-프레미스 메시징 서버에서 필요)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-122">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="1cb66-123">예를 들어, **131.107.2.200**.</span><span class="sxs-lookup"><span data-stu-id="1cb66-123">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="1cb66-124">SPF TXT 레코드에 포함해야하는 모든 제3자 도메인에 사용할 도메인 이름.</span><span class="sxs-lookup"><span data-stu-id="1cb66-124">Domain names to use for all third-party domains that you need to include in your SPF TXT record.</span></span> <span data-ttu-id="1cb66-125">일부 대량 메일 공급자는 고객에게 사용할 하위 도메인을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-125">Some bulk mail providers have set up subdomains to use for their customers.</span></span> <span data-ttu-id="1cb66-126">예를 들어, MailChimp 회사는 **servers.mcsv.net** 을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-126">For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="1cb66-127">SPF TXT 레코드에 사용할 시행 규칙을 정합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-127">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="1cb66-128">**-all** 규칙이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-128">The **-all** rule is recommended.</span></span> <span data-ttu-id="1cb66-129">다른 구문 옵션에 대한 자세한 내용은 [Office 365용 SPF TXT 레코드 구문](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cb66-129">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cb66-130">사용자 지정 도메인을 사용하려면 Office 365에서는 스푸핑을 방지하는 데 도움이 되도록 SPF (Sender Policy Framework) TXT 레코드를 사용자 DNS 레코드에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-130">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="1cb66-131">SPF TXT 레코드 생성 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="1cb66-131">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="1cb66-132">다음 표에서는 SPF 구문을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-132">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="1cb66-133">요소</span><span class="sxs-lookup"><span data-stu-id="1cb66-133">Element</span></span>|<span data-ttu-id="1cb66-134">만약 다음을 사용 중이라면...</span><span class="sxs-lookup"><span data-stu-id="1cb66-134">If you're using...</span></span>|<span data-ttu-id="1cb66-135">고객에게 일반적인가요?</span><span class="sxs-lookup"><span data-stu-id="1cb66-135">Common for customers?</span></span>|<span data-ttu-id="1cb66-136">이 항목을 추가하세요...</span><span class="sxs-lookup"><span data-stu-id="1cb66-136">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="1cb66-137">1</span><span class="sxs-lookup"><span data-stu-id="1cb66-137">1</span></span>|<span data-ttu-id="1cb66-138">모든 전자 메일 시스템 (필수)</span><span class="sxs-lookup"><span data-stu-id="1cb66-138">Any email system (required)</span></span>|<span data-ttu-id="1cb66-139">공통.</span><span class="sxs-lookup"><span data-stu-id="1cb66-139">Common.</span></span> <span data-ttu-id="1cb66-140">이 값으로 시작하는 모든 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="1cb66-140">All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="1cb66-141">2</span><span class="sxs-lookup"><span data-stu-id="1cb66-141">2</span></span>|<span data-ttu-id="1cb66-142">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1cb66-142">Exchange Online</span></span>|<span data-ttu-id="1cb66-143">공통</span><span class="sxs-lookup"><span data-stu-id="1cb66-143">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="1cb66-144">3</span><span class="sxs-lookup"><span data-stu-id="1cb66-144">3</span></span>|<span data-ttu-id="1cb66-145">Exchange Online 전용</span><span class="sxs-lookup"><span data-stu-id="1cb66-145">Exchange Online dedicated only</span></span>|<span data-ttu-id="1cb66-146">공통이 아님</span><span class="sxs-lookup"><span data-stu-id="1cb66-146">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="1cb66-147">4</span><span class="sxs-lookup"><span data-stu-id="1cb66-147">4</span></span>|<span data-ttu-id="1cb66-148">Office 365 독일, Microsoft Cloud 독일 전용</span><span class="sxs-lookup"><span data-stu-id="1cb66-148">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="1cb66-149">공통이 아님</span><span class="sxs-lookup"><span data-stu-id="1cb66-149">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="1cb66-150">5</span><span class="sxs-lookup"><span data-stu-id="1cb66-150">5</span></span>|<span data-ttu-id="1cb66-151">제3자 전자 메일 시스템</span><span class="sxs-lookup"><span data-stu-id="1cb66-151">Third-party email system</span></span>|<span data-ttu-id="1cb66-152">공통이 아님</span><span class="sxs-lookup"><span data-stu-id="1cb66-152">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="1cb66-153">\<domain_name\>은(는) 타사 전자 메일 시스템 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-153">\<domain_name\> is the domain of the third party email system.</span></span>|
   |<span data-ttu-id="1cb66-154">6</span><span class="sxs-lookup"><span data-stu-id="1cb66-154">6</span></span>|<span data-ttu-id="1cb66-155">온-프레미스 전자 메일 시스템</span><span class="sxs-lookup"><span data-stu-id="1cb66-155">On-premises email system.</span></span> <span data-ttu-id="1cb66-156">예를 들어 Exchange Online Protection 및 다른 메일 시스템</span><span class="sxs-lookup"><span data-stu-id="1cb66-156">For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="1cb66-157">공통이 아님</span><span class="sxs-lookup"><span data-stu-id="1cb66-157">Not common</span></span>|<span data-ttu-id="1cb66-158">추가 메일 시스템마다 다음 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-158">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="1cb66-159">\<IP_address\> 및 \<domain_name\>은(는) 도메인을 대신하여 메일을 보내는 다른 전자 메일 시스템의 IP 주소 및 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-159">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="1cb66-160">7</span><span class="sxs-lookup"><span data-stu-id="1cb66-160">7</span></span>|<span data-ttu-id="1cb66-161">모든 전자 메일 시스템 (필수)</span><span class="sxs-lookup"><span data-stu-id="1cb66-161">Any email system (required)</span></span>|<span data-ttu-id="1cb66-162">공통.</span><span class="sxs-lookup"><span data-stu-id="1cb66-162">Common.</span></span> <span data-ttu-id="1cb66-163">이 값으로 끝나는 모든 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="1cb66-163">All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="1cb66-164">다음 여러 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-164">This can be one of several values.</span></span> <span data-ttu-id="1cb66-165">`-all`을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-165">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="1cb66-166">아직 이 작업을 수행하지 않은 경우 다음 표의 구문을 사용하여 SPF TXT 레코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-166">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="1cb66-167">예를 들어, Office 365에서 완전히 호스팅되는 즉, 온-프레미스 메일 서버가 없는 경우, SPF TXT 레코드에는 1, 2 및 7행이 포함되며 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-167">For example, if you are fully-hosted in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="1cb66-168">이것이 가장 일반적인 SPF TXT 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-168">This is the most common SPF TXT record.</span></span> <span data-ttu-id="1cb66-169">이 레코드는 사용자의 Microsoft 데이터 센터가 미국, 유럽 (독일 포함) 또는 다른 위치에 있는지 여부에 관계없이 모든 사람에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-169">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="1cb66-170">그러나 Microsoft Cloud 독일의 일부인 Office 365 Germany를 구매한 경우 2행 대신 4행의 include 문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-170">However, if you have purchased Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2.</span></span> <span data-ttu-id="1cb66-171">예를 들어, Office 365 Germany에서 완전히 호스팅되는 즉, 온-프레미스 메일 서버가 없는 경우, SPF TXT 레코드에는 1, 4 및 7행이 포함되며 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-171">For example, if you are fully-hosted in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="1cb66-172">사용자가 이미 Office 365에 배포되어 있고 사용자 지정 도메인에 대한 SPF TXT 레코드를 설정했고 Office 365 Germany로 마이그레이션하는 경우에는 SPF TXT 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-172">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="1cb66-173">이렇게 하려면 `include:spf.protection.outlook.com` 를 `include:spf.protection.outlook.de`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-173">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="1cb66-174">SPF TXT 레코드를 구성한 후에는 DNS에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-174">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="1cb66-175">도메인에 대해 하나의 SPF TXT 레코드만 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-175">You can only have one SPF TXT record for a domain.</span></span> <span data-ttu-id="1cb66-176">SPF TXT 레코드가 존재하는 경우 새 레코드를 추가하는 대신 기존 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-176">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="1cb66-177">[Office 365용 DNS 레코드 만들기](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)로 이동한 다음 DNS 호스트에 대한 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-177">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then click the link for your DNS host.</span></span>

4. <span data-ttu-id="1cb66-178">사용자의 SPF TXT 레코드를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-178">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="1cb66-179">하위 도메인을 어떻게 처리합니까?</span><span class="sxs-lookup"><span data-stu-id="1cb66-179">How to handle subdomains?</span></span>

<span data-ttu-id="1cb66-180">*하위 도메인은 최상위 도메인의 SPF 레코드를 상속하지 않으므로 각 하위 도메인에 대해 별도의 레코드를 만들어야 합니다*.</span><span class="sxs-lookup"><span data-stu-id="1cb66-180">It is important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top level domain*.</span></span>

<span data-ttu-id="1cb66-181">모든 도메인 및 하위 도메인에 대해 추가 와일드카드 SPF 레코드(`*.`)가 있어야 공격자가 존재하지 않는 하위 도메인에서 보낸다고 주장하는 전자 메일을 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-181">An additional wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="1cb66-182">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="1cb66-182">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="1cb66-183">SPF 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1cb66-183">Troubleshooting SPF</span></span>

<span data-ttu-id="1cb66-184">SPF TXT 레코드에 문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="1cb66-184">Having trouble with your SPF TXT record?</span></span> <span data-ttu-id="1cb66-185">[문제 해결: Office 365의 SPF에 대한 모범 사례](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)를 읽으세요.</span><span class="sxs-lookup"><span data-stu-id="1cb66-185">Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>


## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="1cb66-186">SPF 전자 메일 인증이 실제로 하는 일은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="1cb66-186">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="1cb66-187">SPF는 사용자를 대신하여 메일을 보낼 수 있는 메일 서버를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-187">SPF identifies which mail servers are allowed to send mail on your behalf.</span></span> <span data-ttu-id="1cb66-188">기본적으로 SPF는 DKIM, DMARC 및 Office 365에서 지원하는 기타 기술과 함께 스푸핑 및 피싱을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-188">Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing.</span></span> <span data-ttu-id="1cb66-189">SPF는 사용자 지정 도메인을 대신하여 메일을 보낼 수 있는 메일 서버를 식별하기 위해 DNS에서 사용하는 TXT 레코드에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-189">SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain.</span></span> <span data-ttu-id="1cb66-190">받는 사람의 메일 시스템은 SPF TXT 레코드를 참조하여 사용자 지정 도메인의 메시지가 인증된 메시징 서버에서 온 것인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-190">Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="1cb66-191">예를 들어 사용자 지정 도메인 contoso.com이 Office 365를 사용한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-191">For example, let's say that your custom domain contoso.com uses Office 365.</span></span> <span data-ttu-id="1cb66-192">Office 365 메시징 서버를 사용자 도메인의 정상적인 메일 서버로 나열하는 SPF TXT 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-192">You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain.</span></span> <span data-ttu-id="1cb66-193">수신 메시징 서버가 joe@contoso.com으로부터 메시지를 받으면 서버는 contoso.com의 SPF TXT 레코드를 조회하여 메시지가 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-193">When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid.</span></span> <span data-ttu-id="1cb66-194">수신 서버에서 SPF 레코드에 나열된 Office 365 메시징 서버 이외의 서버에서 받은 메시지를 발견하는 경우 수신 메일 서버에서 메시지를 스팸으로 거부하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-194">If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="1cb66-195">또한 사용자 지정 도메인에 SPF TXT 레코드가 없는 경우 일부 수신 서버에서 메시지를 완전히 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-195">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright.</span></span> <span data-ttu-id="1cb66-196">이는 수신 서버에서 메시지가 인증된 메시징 서버에서 온 것인지 확인할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-196">This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="1cb66-197">사용자가 Office 365용 메일을 이미 설정한 경우 SPF TXT 레코드로 Microsoft 메시징 서버를 DNS에 이미 포함 시켰습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-197">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record.</span></span> <span data-ttu-id="1cb66-198">그러나 DNS에서 SPF TXT 레코드를 업데이트해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-198">However, there are some cases where you may need to update your SPF TXT record in DNS.</span></span> <span data-ttu-id="1cb66-199">예:</span><span class="sxs-lookup"><span data-stu-id="1cb66-199">For example:</span></span>

- <span data-ttu-id="1cb66-200">이전에는 SharePoint Online을 사용하는 경우 다른 SPF TXT 레코드를 사용자 지정 도메인에 추가해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-200">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online.</span></span> <span data-ttu-id="1cb66-201">이 작업은 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-201">This is no longer required.</span></span> <span data-ttu-id="1cb66-202">이렇게 변경하면 정크 메일 폴더에 SharePoint Online 알림 메시지가 표시될 위험이 줄어 듭니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-202">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="1cb66-203">조회 제한 10개에 도달하여 "조회 제한 초과" 및 "너무 많은 홉"과 같은 오류가 발생하는 경우 SPF TXT 레코드를 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="1cb66-203">Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="1cb66-204">Office 365 및 Exchange 온-프레미스의 하이브리드 환경이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="1cb66-204">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="1cb66-205">DKIM 및 DMARC (권장)를 설정하려고합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-205">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="1cb66-206">SPF에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="1cb66-206">More information about SPF</span></span>

<span data-ttu-id="1cb66-207">지원되는 SPF 구문, 스푸핑, 문제 해결 및 Office 365에서 SPF를 지원하는 방법에 대한 자세한 내용과 고급 예제를 보려면 [SPF가 Office 365에서 스푸핑 및 피싱을 방지하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cb66-207">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="links-to-configure-dkim-and-dmarc"></a><span data-ttu-id="1cb66-208">DKIM 및 DMARC를 구성하는 링크</span><span class="sxs-lookup"><span data-stu-id="1cb66-208">Links to configure DKIM and DMARC</span></span>

 <span data-ttu-id="1cb66-209">SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-209">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="1cb66-210">이 같은 기술로부터 방어하려면 SPF를 설정한 후에 Office 365용 DKIM 및 DMARC를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-210">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="1cb66-211">[DKIM](use-dkim-to-validate-outbound-email.md) 전자 메일 인증의 목표는 전자 메일 내용이 위조되지 않았다는 것을 증명하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-211">[DKIM](use-dkim-to-validate-outbound-email.md) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="1cb66-212">[DMARC](use-dmarc-to-validate-email.md) 전자 메일 인증의 목표는 SPF 및 DKIM 정보가 보낸 주소와 일치하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb66-212">[DMARC](use-dmarc-to-validate-email.md) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>
