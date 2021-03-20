---
title: Microsoft 365에 도메인 연결
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365로 도메인을 확인하고 DNS 레코드 만드는 방법을 배웁니다.
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: 506ee887edbc59956aee11059a7085bc4b22624e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914597"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="70d6b-103">Microsoft 365에 도메인 연결</span><span class="sxs-lookup"><span data-stu-id="70d6b-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="70d6b-104">도메인을 추가하지 않으면 추가할 때까지 조직의 사용자가 전자 메일 주소로 onmicrosoft.com 도메인을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="70d6b-105">사용자를 두 번 설정하지 않아도 되도록 사용자를 추가하기 전에 도메인을 추가하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="70d6b-106">원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.yml)하세요.</span><span class="sxs-lookup"><span data-stu-id="70d6b-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="70d6b-107">사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="70d6b-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="70d6b-108">관리 센터 도메인 설정 마법사에서 MX 레코드에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="70d6b-109">호스팅 공급자의 웹 사이트에서 새 MX 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="70d6b-110">필드가 다음 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="70d6b-111">레코드 종류: `MX`</span><span class="sxs-lookup"><span data-stu-id="70d6b-111">Record Type: `MX`</span></span>
- <span data-ttu-id="70d6b-112">우선순위: 사용 가능한 가장 높은 값(일반적으로 `0`)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="70d6b-113">호스트 이름: `@`</span><span class="sxs-lookup"><span data-stu-id="70d6b-113">Host Name: `@`</span></span>
- <span data-ttu-id="70d6b-114">대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="70d6b-115">TTL: `3600‎`(또는 공급자 기본값)</span><span class="sxs-lookup"><span data-stu-id="70d6b-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="70d6b-116">레코드를 저장한 다음 다른 모든 MX 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="70d6b-117">CNAME 레코드를 추가하여 사용자를 사서함에 연결</span><span class="sxs-lookup"><span data-stu-id="70d6b-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="70d6b-118">관리 센터 도메인 설정 마법사에서 CNAME 레코드에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="70d6b-119">호스팅 공급자의 웹 사이트에서 다음 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="70d6b-120">필드가 각각 다음 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="70d6b-121">레코드 종류: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="70d6b-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="70d6b-122">호스트: 여기에 관리 센터에서 복사한 값을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="70d6b-123">대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="70d6b-124">TTL: `3600‎`(또는 공급자 기본값)</span><span class="sxs-lookup"><span data-stu-id="70d6b-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="70d6b-125">스팸 방지에 유용한 TXT 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="70d6b-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="70d6b-126">**시작하기 전에:** 도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="70d6b-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="70d6b-127">대신, 필수 Microsoft 365 값을 호스팅 공급자 웹 사이트의 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="70d6b-128">호스팅 공급자의 웹 사이트에서 기존 SPF 레코드를 편집하거나 SPF 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="70d6b-129">필드가 다음 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="70d6b-130">레코드 종류: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="70d6b-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="70d6b-131">호스트: `@`</span><span class="sxs-lookup"><span data-stu-id="70d6b-131">Host: `@`</span></span>
- <span data-ttu-id="70d6b-132">TXT 값: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="70d6b-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="70d6b-133">TTL: `3600‎`(또는 공급자 기본값)</span><span class="sxs-lookup"><span data-stu-id="70d6b-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="70d6b-134">레코드를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-134">Save the record.</span></span>

<span data-ttu-id="70d6b-135">이러한 [SPF 유효성 검사 도구](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 중 하나를 사용하여 SPF 레코드의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-135">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="70d6b-136">SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="70d6b-137">이 같은 기술로부터 보호하려면 SPF를 설정한 후에 Microsoft 365의 DKIM 및 DMARC도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="70d6b-138">시작하려면 [DKIM을 사용하여 Microsoft 365의 도메인에서 보낸 발신 전자 메일의 유효성 검사하기](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) 및 [DMARC를 사용하여 Microsoft 365에서 전자 메일의 유효성 검사하기](../../security/office-365-security/use-dmarc-to-validate-email.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70d6b-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span></span>

<span data-ttu-id="70d6b-139">마지막으로 관리 센터 도메인 설정 마법사로 돌아가 설정을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="70d6b-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>