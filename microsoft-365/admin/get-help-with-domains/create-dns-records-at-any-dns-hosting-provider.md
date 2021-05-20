---
title: DNS 레코드를 추가하여 도메인 연결하기
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
description: 도메인을 확인하고 등록 기관 계정에서 DNS 레코드를 업데이트하여 DNS 호스팅 공급자의 도메인을 Microsoft 365에 연결합니다.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: facdd460bd3197e39dd6d4d9f4a5450dc972bf03
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537562"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="a050c-103">DNS 레코드를 추가하여 도메인 연결하기</span><span class="sxs-lookup"><span data-stu-id="a050c-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="a050c-104">타사 호스팅 공급자로부터 도메인을 구매한 경우에는 등록 기관 계정에서 DNS 레코드를 업데이트하여 Microsoft 365에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="a050c-105">이 단계를 마치면 도메인은 도메인을 구매한 호스트에 등록된 상태로 유지되지만, Microsoft 365는 도메인을 전자 메일 주소(예: user@yourdomain.com) 및 기타 서비스에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="a050c-106">도메인을 추가하지 않으면 추가할 때까지 조직의 사용자가 전자 메일 주소로 onmicrosoft.com 도메인을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="a050c-107">사용자를 두 번 설정하지 않아도 되도록 사용자를 추가하기 전에 도메인을 추가하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="a050c-108">원하는 정보를 찾지 못한 경우 [도메인 FAQ를 확인](../setup/domains-faq.yml)하세요.</span><span class="sxs-lookup"><span data-stu-id="a050c-108">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="a050c-109">1단계: TXT 또는 MX 레코드를 추가하여 도메인을 소유하고 있는지 확인하기</span><span class="sxs-lookup"><span data-stu-id="a050c-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="a050c-110">권장: TXT 레코드로 확인</span><span class="sxs-lookup"><span data-stu-id="a050c-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="a050c-111">먼저 Microsoft 365에 추가하려는 도메인을 소유하고 있다는 사실을 증명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="a050c-112">[Microsoft 365 관리 센터](https://admin.microsoft.com/)에 로그인하고 **모두 보기** > **설정** > **도메인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="a050c-113">새 브라우저 탭 또는 창에서 내 DNS 호스팅 공급자에 로그인한 다음 DNS 설정 관리 위치(예: 영역 파일 설정, 도메인 관리, 도메인 관리자, DNS 관리자)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="a050c-114">공급자의 DNS 관리자 페이지로 이동하고 관리 센터에 표시된 TXT 레코드를 도메인에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="a050c-115">이 레코드를 추가해도 기존 저낮 메일이나 기타 서비스에 영향을 주지 않으며, 도메인이 Microsoft 365에 연결되면 안전하게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="a050c-116">예제:</span><span class="sxs-lookup"><span data-stu-id="a050c-116">Example:</span></span>
- <span data-ttu-id="a050c-117">TXT 이름: `@`</span><span class="sxs-lookup"><span data-stu-id="a050c-117">TXT Name: `@`</span></span>
- <span data-ttu-id="a050c-118">TXT 값: MS=ms########(관리 센터의 고유 ID)</span><span class="sxs-lookup"><span data-stu-id="a050c-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="a050c-119">TTL: `3600‎`(또는 공급자 기본값)</span><span class="sxs-lookup"><span data-stu-id="a050c-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="a050c-120">레코드를 저장하고 관리 센터로 돌아간 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="a050c-121">일반적으로 레코드가 변경 내용을 등록하는 데 15분 정도 걸리지만, 때로는 시간이 더 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="a050c-122">시간을 좀 두고 몇 번 정도 시도하면 변경 내용을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="a050c-123">Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="a050c-124">MX 레코드로 확인</span><span class="sxs-lookup"><span data-stu-id="a050c-124">Verify with an MX record</span></span>

<span data-ttu-id="a050c-125">등록 기관에서 TXT 레코드 추가를 지원하지 않으면 MX 레코드를 추가하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="a050c-126">[Microsoft 365 관리 센터](https://admin.microsoft.com/)에 로그인하고 **모두 보기** > **설정** > **도메인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="a050c-127">새 브라우저 탭 또는 창에서 내 DNS 호스팅 공급자에 로그인한 다음 DNS 설정 관리 위치(예: 영역 파일 설정, 도메인 관리, 도메인 관리자, DNS 관리자)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="a050c-128">공급자의 DNS 관리자 페이지로 이동하고 관리 센터에 표시된 MX 레코드를 도메인에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="a050c-129">이 MX 레코드의 **우선 순위** 는 도메인에 대한 모든 기존 MX 레코드의 최상위여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="a050c-130">그렇지 않으면 전자 메일 보내기와 받기를 방해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="a050c-131">도메인 확인이 완료되면 즉시 이 레코드를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="a050c-132">필드가 다음 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="a050c-133">레코드 종류: `MX`</span><span class="sxs-lookup"><span data-stu-id="a050c-133">Record Type: `MX`</span></span>
- <span data-ttu-id="a050c-134">우선순위: 사용 가능한 가장 높은 값(일반적으로 `0`)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="a050c-135">호스트 이름: `@`</span><span class="sxs-lookup"><span data-stu-id="a050c-135">Host Name: `@`</span></span>
- <span data-ttu-id="a050c-136">대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="a050c-137">TTL: `3600‎`(또는 공급자 기본값)</span><span class="sxs-lookup"><span data-stu-id="a050c-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="a050c-138">Microsoft에서 올바른 MX 레코드를 찾으면 도메인이 확인된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="a050c-139">2단계: DNS 레코드를 추가하여 Microsoft 서비스 연결하기</span><span class="sxs-lookup"><span data-stu-id="a050c-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="a050c-140">새 브라우저 탭 또는 창에서 내 DNS 호스팅 공급자에 로그인하여 DNS 설정 관리 위치(예: 영역 파일 설정, 도메인 관리, 도메인 관리자, DNS 관리자)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="a050c-141">사용하려는 서비스에 따라 여러 가지 유형의 DNS 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="a050c-142">전자 메일에 MX 레코드 추가하기(Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="a050c-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="a050c-143">**시작 하기 전에**: 사용자가 도메인에 전자 메일(예: user@yourdomain.com)을 이미 가지고 있는 경우에는 MX 레코드를 설정하기 전에 관리 센터에서 사용자의 계정을 만드세요.</span><span class="sxs-lookup"><span data-stu-id="a050c-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="a050c-144">그러면 전자 메일을 계속 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="a050c-145">도메인의 MX 레코드를 업데이트하면 해당 도메인을 사용하는 사용자의 모든 새 전자 메일이 이제 Microsoft 365로 옵니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="a050c-146">[전자 메일 및 연락처를 Microsoft 365로 마이그레이션하기](../setup/migrate-email-and-contacts-admin.md)로 결정한 경우가 아니면, 이미 가지고 있는 전자 메일은 현재 전자 메일 호스트에 남습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="a050c-147">관리 센터 도메인 설정 마법사에서 MX 레코드에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="a050c-148">호스팅 공급자의 웹 사이트에서 새 MX 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="a050c-149">필드가 다음 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="a050c-150">레코드 종류: `MX`</span><span class="sxs-lookup"><span data-stu-id="a050c-150">Record Type: `MX`</span></span>
- <span data-ttu-id="a050c-151">우선순위: 사용 가능한 가장 높은 값(일반적으로 `0`)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="a050c-152">호스트 이름: `@`</span><span class="sxs-lookup"><span data-stu-id="a050c-152">Host Name: `@`</span></span>
- <span data-ttu-id="a050c-153">대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="a050c-154">TTL: `3600‎`(또는 공급자 기본값)</span><span class="sxs-lookup"><span data-stu-id="a050c-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="a050c-155">레코드를 저장한 다음 다른 모든 MX 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="a050c-156">CNAME 레코드를 추가하여 다른 서비스(Teams, Exchange Online, AAD, MDM)에 연결하기</span><span class="sxs-lookup"><span data-stu-id="a050c-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="a050c-157">관리 센터 도메인 설정 마법사에서 CNAME 레코드에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="a050c-158">호스팅 공급자의 웹 사이트에서 연결할 각 서비스에 대한 CNAME 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="a050c-159">필드가 각각 다음 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="a050c-160">레코드 종류: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="a050c-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="a050c-161">호스트: 여기에 관리 센터에서 복사한 값을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="a050c-162">대상 주소: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="a050c-163">TTL: `3600‎`(또는 공급자 기본값)</span><span class="sxs-lookup"><span data-stu-id="a050c-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="a050c-164">SPF TXT 레코드를 추가하거나 편집하여 전자 메일 스팸 방지하기(Outlook, Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="a050c-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="a050c-165">**시작하기 전에:** 도메인에 이미 SPF 레코드가 있는 경우 Microsoft 365의 새 SPF 레코드를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a050c-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="a050c-166">대신, 필수 Microsoft 365 값을 호스팅 공급자 웹 사이트의 현재 레코드에 추가하여 두 값 집합을 모두 포함하는 *단일* SPF 레코드가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="a050c-167">호스팅 공급자의 웹 사이트에서 기존 SPF 레코드를 편집하거나 SPF 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="a050c-168">필드가 다음 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="a050c-169">레코드 종류: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="a050c-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="a050c-170">호스트: `@`</span><span class="sxs-lookup"><span data-stu-id="a050c-170">Host: `@`</span></span>
- <span data-ttu-id="a050c-171">TXT 값: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="a050c-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="a050c-172">TTL: `3600‎`(또는 공급자 기본값)</span><span class="sxs-lookup"><span data-stu-id="a050c-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="a050c-173">레코드를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-173">Save the record.</span></span>

<span data-ttu-id="a050c-174">이러한 [SPF 유효성 검사 도구](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 중 하나를 사용하여 SPF 레코드의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-174">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="a050c-175">SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="a050c-176">이 같은 기술로부터 보호하려면 SPF를 설정한 후에 Microsoft 365의 DKIM 및 DMARC도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="a050c-177">시작하려면 [DKIM을 사용하여 Microsoft 365의 도메인에서 보낸 발신 전자 메일의 유효성 검사하기](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) 및 [DMARC를 사용하여 Microsoft 365에서 전자 메일의 유효성 검사하기](../../security/office-365-security/use-dmarc-to-validate-email.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a050c-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="a050c-178">커뮤니케이션 서비스(Teams, 비즈니스용 Skype)에 대한 SRV 레코드 추가하기</span><span class="sxs-lookup"><span data-stu-id="a050c-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="a050c-179">호스팅 공급자의 웹 사이트에서 연결할 각 서비스에 대한 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="a050c-180">필드가 각각 다음 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="a050c-181">레코드 종류: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="a050c-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="a050c-182">이름: `@`</span><span class="sxs-lookup"><span data-stu-id="a050c-182">Name: `@`</span></span>
- <span data-ttu-id="a050c-183">대상: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="a050c-184">프로토콜: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="a050c-185">서비스: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="a050c-186">우선순위: `100`</span><span class="sxs-lookup"><span data-stu-id="a050c-186">Priority: `100`</span></span>
- <span data-ttu-id="a050c-187">가중치: `1`</span><span class="sxs-lookup"><span data-stu-id="a050c-187">Weight: `1`</span></span>
- <span data-ttu-id="a050c-188">포트: 관리 센터에서 값을 복사하여 여기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="a050c-189">TTL: `3600‎`(또는 공급자 기본값)</span><span class="sxs-lookup"><span data-stu-id="a050c-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="a050c-190">레코드를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="a050c-191">SRV 레코드 필드 제한 사항 및 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a050c-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="a050c-192">일부 호스팅 공급자는 SRV 레코드 내에서 필드 값에 제한을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="a050c-193">이러한 제한 사항에 대한 몇 가지 일반적인 해결 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="a050c-194">이름</span><span class="sxs-lookup"><span data-stu-id="a050c-194">Name</span></span>
<span data-ttu-id="a050c-195">호스팅 공급자가 이 필드를 **@** 으로 설정하는 것을 허용하지 않는 경우 이 필드를 비워 두세요. </span><span class="sxs-lookup"><span data-stu-id="a050c-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="a050c-196">호스팅 공급자에 서비스 및 프로토콜 값에 대한 별도의 필드가 있는 경우 *에만* 이 방법을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a050c-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="a050c-197">그렇지 않으면 아래의 서비스 및 프로토콜 정보를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a050c-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="a050c-198">서비스 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="a050c-198">Service and Protocol</span></span>
<span data-ttu-id="a050c-199">호스팅 공급자가 SRV 레코드에 이러한 필드를 제공하지 않으면 레코드의 **이름** 필드에 **서비스** 및 **프로토콜** 값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="a050c-200">(참고: 호스팅 공급자에 따라 **이름** 필드는 **호스트**, **호스트 이름** 또는 **하위 도메인** 과 같은 다른 이름으로 불릴 수 있습니다.) 이러한 값을 추가하려면 값을 점으로 구분하여 단일 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="a050c-201">예: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="a050c-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="a050c-202">우선순위, 가중치 및 포트</span><span class="sxs-lookup"><span data-stu-id="a050c-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="a050c-203">호스팅 공급자가 SRV 레코드에 이러한 필드를 제공하지 않으면 레코드의 **대상** 필드에 이를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="a050c-204">(참고: 호스팅 공급자에 따라 **대상** 필드는 **콘텐츠**, **IP 주소** 또는 **대상 호스트** 와 같이 다른 이름으로 불릴 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="a050c-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="a050c-205">이러한 값을 추가하려면 값을 공백으로 구분하고 *때로는 점으로 끝나는* 단일 문자열을 만듭니다(확실하지 않은 경우 공급자에게 문의).</span><span class="sxs-lookup"><span data-stu-id="a050c-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="a050c-206">값은 우선 순위, 무게, 포트, 대상 순서로 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a050c-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="a050c-207">예제 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="a050c-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="a050c-208">예제 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="a050c-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>

## <a name="related-content"></a><span data-ttu-id="a050c-209">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="a050c-209">Related content</span></span>

<span data-ttu-id="a050c-210">[모든 도메인 등록 기관에서 Microsoft 365를 설정하도록 네임 서버 변경 ](change-nameservers-at-any-domain-registrar.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="a050c-210">[Change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md) (article)</span></span>

<span data-ttu-id="a050c-211">[도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 수정](find-and-fix-issues.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="a050c-211">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>

<span data-ttu-id="a050c-212">[도메인 관리](index.yml)(링크 페이지)</span><span class="sxs-lookup"><span data-stu-id="a050c-212">[Manage domains](index.yml) (link page)</span></span>