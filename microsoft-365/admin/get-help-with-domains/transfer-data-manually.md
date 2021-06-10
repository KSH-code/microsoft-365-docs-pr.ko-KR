---
title: 두 계정 간에 수동으로 데이터 전송
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 계획 또는 회사 이름을 변경하거나 여러 구독을 결합한 경우 두 개의 Microsoft 365 계정 간에 데이터를 수동으로 전송하는 방법을 찾아 찾습니다.
ms.openlocfilehash: f9b9185a2441c4fc47aef0d3ce28116ff4e33e6e
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297107"
---
# <a name="transfer-data-manually-between-two-accounts"></a><span data-ttu-id="9b3e7-103">두 계정 간에 수동으로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="9b3e7-103">Transfer data manually between two accounts</span></span>

<span data-ttu-id="9b3e7-104">일정에서 여유 시간을 균등하게 롤아웃할 준비를 합니다. 두 개의 Microsoft 365 계정 간에 데이터를 전송하는 것은 수동, 복잡하고 시간이 많이 걸리는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-104">Prepare to roll up your sleeves and block out a chunk of time on your calendar: transferring data between two Microsoft 365 accounts is a manual, complicated, and time-consuming process.</span></span> <span data-ttu-id="9b3e7-105">이 프로세스는 자동화되거나 지원되는 프로세스가 아니며,</span><span class="sxs-lookup"><span data-stu-id="9b3e7-105">This is not an automated or supported process.</span></span> <span data-ttu-id="9b3e7-106">시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-106">We'll get you started.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="9b3e7-107">전자 메일, 메일 및 비즈니스용 Skype 호스트된 공개 웹 사이트가 작동하지 Microsoft 365 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-107">There will be down time during the process where email, Skype for Business and a public website hosted on Microsoft 365 won't work.</span></span> <span data-ttu-id="9b3e7-108">사용자는 새 사용자 이름과 암호를 얻게 며 사용자 이름과 암호를 다시 설정해야 Outlook.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-108">Users will get new user names and passwords, and they'll need to reset up Outlook.</span></span>

<span data-ttu-id="9b3e7-109">**다음 중 하나를 적용하는 경우 이 항목의 지침을 사용하여 수동으로 데이터를 전송합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-109">**Only transfer data manually using the instructions in this topic if one of the following applies:**</span></span>
  
- <span data-ttu-id="9b3e7-110">다른 서비스 패밀리의 계획으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-110">You need to change to a plan in a different service family.</span></span>

- <span data-ttu-id="9b3e7-111">회사 이름이 변경된 후 다른 초기 도메인 이름을 사용하려는 경우 새 구독을 만들고 데이터를 마이그레이션하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-111">Your company name changed, and you decided to create a new subscription and migrate your data because you want to use different initial domain names.</span></span>

- <span data-ttu-id="9b3e7-112">여러 구독을 하나의 새 구독으로 결합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-112">You need to combine multiple subscriptions into one new one.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b3e7-113">구독 계획을 [](../../commerce/subscriptions/switch-to-a-different-plan.md) 변경해야 하는 경우 요금제 전환 마법사를 사용할 수 있습니다. 또는 요금제 전환 마법사가 작동하지 않는 경우에도 동일한 구독 패밀리의 새 구독 요금제로 이전해야 하는 경우 데이터를 수동으로 전송할 필요가 없습니다. 작동이 종료되는 시간도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-113">If you need to [change your subscription plan](../../commerce/subscriptions/switch-to-a-different-plan.md) and can use the Switch plans wizard, or if you need to transfer to a new subscription plan in the same subscription family even when the Switch plans wizard doesn't work, you don't need to manually transfer your data, and there is no down time.</span></span>

|<span data-ttu-id="9b3e7-114">**Tasks**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-114">**Tasks**</span></span>|<span data-ttu-id="9b3e7-115">**Steps**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-115">**Steps**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9b3e7-116">이동하려는 계획을 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-116">Purchase the plan you want to move to.</span></span>  <br/> |<span data-ttu-id="9b3e7-117">등록할 때 초기 도메인 이름에 사용할 회사 이름(예: *yourcompany* .onmicrosoft.com, *yourcompany* -public.sharepoint.com 및 *.sharepoint.com.*</span><span class="sxs-lookup"><span data-stu-id="9b3e7-117">When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com.</span></span> <span data-ttu-id="9b3e7-118">기존 구독과는  *다른company*  이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-118">You need to use a different  *yourcompany*  name than you did for any existing subscriptions.</span></span>  <br/> <span data-ttu-id="9b3e7-119">> [!NOTE]> 일반적으로 시스템에서  *yourcompany를*  사용하는 초기 도메인 이름을 해제하기 위해 구독을 취소한 후 최소 몇 개월이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-119">> [!NOTE]>  It typically takes a minimum of several months after cancelling a subscription to release the initial domain names that use  *yourcompany*  from our systems.</span></span> <span data-ttu-id="9b3e7-120">이전 Microsoft 365 구독의 모든 데이터를 저장하고 해당 구독을 취소하는 경우에도 *이전company* 값을 새 구독에서 즉시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-120">Even if you plan to save all your data from your old Microsoft 365 subscription, and cancel that subscription, the old  *yourcompany*  value is not immediately available for use in a new subscription.</span></span>           |
|<span data-ttu-id="9b3e7-121">이전 구독에서 사용자 지정 도메인을 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-121">Remove your custom domain from your old Microsoft 365 subscription.</span></span>  <br/> | <span data-ttu-id="9b3e7-122">도메인을 [](remove-a-domain.md) 제거하기 전에 필요한 단계에 따라 사용자 전자 메일 주소에서 도메인 이름을 제거하고 전자 메일 및 사용자 지정 도메인의 Lync에 대한 DNS 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-122">Follow the [required steps before you remove a domain](remove-a-domain.md) to remove the domain name from user email addresses and remove DNS records for email and Lync for the custom domain.</span></span> <span data-ttu-id="9b3e7-123">공용 웹 사이트를 Microsoft 365 CNAME 레코드도 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-123">If you host your public website on Microsoft 365, you'll also need to remove the CNAME record that points to it.</span></span>  <br/> <span data-ttu-id="9b3e7-124">> [!IMPORTANT]> 전자 메일을 이 사용자 지정 도메인으로 라우팅하는 MX 레코드를 제거하면 새 계정에 도메인을 추가하고 새 MX 레코드를 설정하고 사용자를 설정할 때까지 전자 메일의 작동이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-124">> [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users.</span></span> <span data-ttu-id="9b3e7-125">Lync에 대한 DNS 레코드를 제거하면 Lync의 작동이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-125">When you remove the DNS records for Lync, Lync will stop working.</span></span> <span data-ttu-id="9b3e7-126">또한 공개 웹 사이트를 포인트로 하는 CNAME 레코드를 제거하면 해당 레코드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-126">And after you remove the CNAME record that points to your public website, it will not be available.</span></span>           <span data-ttu-id="9b3e7-127">[도메인을 제거합니다.](remove-a-domain.md)</span><span class="sxs-lookup"><span data-stu-id="9b3e7-127">[Remove the domain](remove-a-domain.md) .</span></span>  <br/> |
|<span data-ttu-id="9b3e7-128">새 구독에 대한 사용자 지정 도메인을 설정하고 사용자를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-128">Set up your custom domain for your new subscription, and set up your users.</span></span>  <br/> | <span data-ttu-id="9b3e7-129">사용자 지정 도메인에 필요한 DNS 레코드 만들기를 포함하여 새 구독을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-129">Set up your new subscription, including creating the required DNS records for your custom domain.</span></span>  <br/>  <span data-ttu-id="9b3e7-130">사용자 지정 도메인의 전자 메일 주소를 사용하여 사용자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-130">Create your users, with email addresses on your custom domain.</span></span>  <br/> |
|<span data-ttu-id="9b3e7-131">이전 구독에서 새 구독으로 데이터를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-131">Transfer data from your old subscription to your new subscription.</span></span>  <br/> | <span data-ttu-id="9b3e7-132">별도의 브라우저 창에서 두 계정 모두에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-132">Sign in to both accounts in separate browser windows:</span></span>  <br/>  <span data-ttu-id="9b3e7-133">브라우저 아이콘을 마우스 오른쪽 단추로 클릭하고 두 개의 개인 브라우저 창을 여는 방법을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-133">Right-click your browser icon, and open two private browser windows.</span></span> <span data-ttu-id="9b3e7-134">두 창에서 서로 다른 자격 증명을 사용하여 두 계정 모두에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-134">You can use different credentials in the two windows to sign in on both accounts.</span></span>  <br/> [<span data-ttu-id="9b3e7-135">구독 간에 관리 설정 전송</span><span class="sxs-lookup"><span data-stu-id="9b3e7-135">Transfer administrative settings between subscriptions</span></span>](#email) <br/> [<span data-ttu-id="9b3e7-136">팀 사이트 구조 및 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="9b3e7-136">Transfer team site structure and data</span></span>](#transfer-team-site-structure-and-data) <br/> [<span data-ttu-id="9b3e7-137">구독 간에 공개 웹 사이트 전송</span><span class="sxs-lookup"><span data-stu-id="9b3e7-137">Transfer a public website between subscriptions</span></span>](#transfer-a-public-website-between-subscriptions) <br/> [<span data-ttu-id="9b3e7-138">구독 간에 관리 설정 전송</span><span class="sxs-lookup"><span data-stu-id="9b3e7-138">Transfer administrative settings between subscriptions</span></span>](#email) <br/> |
|<span data-ttu-id="9b3e7-139">Microsoft Support for Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-139">Cancel the subscription for the plan you're done with by calling Microsoft Support for Microsoft 365.</span></span>  <br/> | <span data-ttu-id="9b3e7-140">새 구독이 작동 중이고 모든 데이터가 전송된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-140">Verify that your new subscription is working and all data has been transferred.</span></span>  <br/>  <span data-ttu-id="9b3e7-141">[고객 지원에 문의하여](../../business-video/get-help-support.md) 이전 구독을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-141">[Contact customer support](../../business-video/get-help-support.md) to cancel your old subscription.</span></span>  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a><span data-ttu-id="9b3e7-142">구독 간에 관리 설정 전송</span><span class="sxs-lookup"><span data-stu-id="9b3e7-142">Transfer administrative settings between subscriptions</span></span>

<span data-ttu-id="9b3e7-143">각 계정의 다음 페이지로 이동하여 이전 계정의 설정에 따라 새 계정을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-143">Go to the following pages on each account, and set up the new account based on the old account's settings.</span></span>
  
<span data-ttu-id="9b3e7-144">중소기업 또는 Microsoft 365 Microsoft 365 데이터를 전송하는 Microsoft 365 Enterprise 페이지는 다르게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-144">If you are transferring data from Microsoft 365 to Microsoft 365 Midsize Business or Microsoft 365 Enterprise, the admin pages are structured differently.</span></span> <span data-ttu-id="9b3e7-145">비디오 [시청:](../index.yml)Microsoft 365 Enterprise 소개하고 다음 위치로 이동하여 관리자 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-145">Watch a [Video: Introducing Microsoft 365 Enterprise](../index.yml), and go to the following places to look at admin settings.</span></span>
  
<span data-ttu-id="9b3e7-146">비즈니스 Microsoft 365 Enterprise Microsoft 365 비즈니스용:</span><span class="sxs-lookup"><span data-stu-id="9b3e7-146">For Microsoft 365 Enterprise and Microsoft 365 Midsize Business:</span></span>
  
|<span data-ttu-id="9b3e7-147">**위치**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-147">**Location**</span></span>|<span data-ttu-id="9b3e7-148">**용도**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-148">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9b3e7-149">**관리자** \> **Microsoft 365** \> **서비스 설정**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-149">**Admin** \> **Microsoft 365** \> **Service settings**</span></span> <br/> |<span data-ttu-id="9b3e7-150">메일, 사이트, Lync, 사용자 소프트웨어, 암호, 커뮤니티, 권한 관리 및 모바일에 대한 설정에 대해 각 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-150">Select each tab for settings for mail, sites, Lync, user software, passwords, community, rights management, and mobile.</span></span>  <br/> |
|<span data-ttu-id="9b3e7-151">**관리자** \> **Exchange**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-151">**Admin** \> **Exchange**</span></span> <br/> | <span data-ttu-id="9b3e7-152">Exchange Online 설정</span><span class="sxs-lookup"><span data-stu-id="9b3e7-152">Exchange Online settings</span></span>  <br/> |
|<span data-ttu-id="9b3e7-153">**관리자** \> **SharePoint**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-153">**Admin** \> **SharePoint**</span></span> <br/> | <span data-ttu-id="9b3e7-154">SharePoint 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="9b3e7-154">SharePoint Online settings</span></span>  <br/> |
|<span data-ttu-id="9b3e7-155">**관리자** \> **비즈니스용 Skype**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-155">**Admin** \> **Skype for Business**</span></span> <br/> |<span data-ttu-id="9b3e7-156">추가 비즈니스용 Skype 설정</span><span class="sxs-lookup"><span data-stu-id="9b3e7-156">Additional Skype for Business settings</span></span>  <br/> |

<span data-ttu-id="9b3e7-157">Microsoft 365 중소기업용</span><span class="sxs-lookup"><span data-stu-id="9b3e7-157">For Microsoft 365 Small Business</span></span>
  
|<span data-ttu-id="9b3e7-158">**위치**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-158">**Location**</span></span>|<span data-ttu-id="9b3e7-159">**용도**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-159">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9b3e7-160">**관리자** \> **조직 전체 설정 관리**</span><span class="sxs-lookup"><span data-stu-id="9b3e7-160">**Admin** \> **Manage organization-wide settings**</span></span> <br/> |<span data-ttu-id="9b3e7-161">관리 설정</span><span class="sxs-lookup"><span data-stu-id="9b3e7-161">Administrative settings</span></span>  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a><span data-ttu-id="9b3e7-162">구독 간에 공개 웹 사이트 전송</span><span class="sxs-lookup"><span data-stu-id="9b3e7-162">Transfer a public website between subscriptions</span></span>

<span data-ttu-id="9b3e7-163">공용 웹 사이트가 Microsoft 365 경우 웹 사이트를 저장하고 새 구독에서 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-163">If you have a public website hosted on Microsoft 365, you need to save it and re-create it on your new subscription.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b3e7-164">공개 웹 사이트가 DNS 호스팅 공급자에서 호스팅되는 경우 변경이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-164">If your public website is hosted at a DNS hosting provider, no changes are required.</span></span> <span data-ttu-id="9b3e7-165">전환의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-165">It will not be affected by your transition.</span></span>
  
<span data-ttu-id="9b3e7-166">SharePoint Online 환경에서 파일 공유 또는 로컬 컴퓨터로 문서 라이브러리 또는 목록 콘텐츠를 저장하려면 SharePoint Online 콘텐츠의 수동 마이그레이션을 [참조하세요.](/sharepoint/troubleshoot/migration-tool/content-manual-migration)</span><span class="sxs-lookup"><span data-stu-id="9b3e7-166">To save a document library or list content from a SharePoint Online environment to file shares or to a local computer, see [Manual migration of SharePoint Online content](/sharepoint/troubleshoot/migration-tool/content-manual-migration).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b3e7-167">공용 사이트 마이그레이션 앱은 데이터를 다른 구독으로 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-167">The Public site migration app can't transfer data to a different subscription.</span></span>
  
## <a name="transfer-team-site-structure-and-data"></a><span data-ttu-id="9b3e7-168">팀 사이트 구조 및 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="9b3e7-168">Transfer team site structure and data</span></span>

<span data-ttu-id="9b3e7-169">팀 사이트 데이터를 저장하거나 전송하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-169">There are several ways to save or transfer team site data:</span></span>
  
- <span data-ttu-id="9b3e7-170">이전 사이트를 서식 파일로 저장하고 서식 파일을 새 사이트로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-170">You can save the old site as a template and import the template into the new site.</span></span>

- <span data-ttu-id="9b3e7-171">문서를 전송하려면 먼저 새 사이트에서 계층 구조를 수동으로 다시 만드면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-171">To transfer documents, first manually recreate your hierarchy on the new site.</span></span> <span data-ttu-id="9b3e7-172">그런 다음 두 팀 SharePoint 동시에 열고 탐색기를 사용하여 두 문서 라이브러리를 모두 Windows 복사하여 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-172">Then you can open both SharePoint team sites at the same time, open both document libraries with Windows Explorer, and copy and paste the documents.</span></span> <span data-ttu-id="9b3e7-173">비디오: 탐색기에서 열기를 사용하여 라이브러리 파일 복사 [또는 이동을 참조합니다.](../../business-video/store-files.md)</span><span class="sxs-lookup"><span data-stu-id="9b3e7-173">See [Video: Copy or move library files by using Open with Explorer](../../business-video/store-files.md).</span></span>

- <span data-ttu-id="9b3e7-174">목록 데이터를 전송하기 위해 목록 서식 파일 을 [저장하고](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)저장된 서식 파일을 사용하여 새 사이트에서 목록을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-174">To transfer list data, save a [list template](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393), and use the saved template to re-create the list on the new site.</span></span>

- <span data-ttu-id="9b3e7-175">SharePoint Online 환경(비즈니스용 OneDrive 또는 팀 사이트)에서 파일 공유 또는 로컬 컴퓨터에 문서 라이브러리 또는 목록 콘텐츠를 저장하려면 SharePoint Online 콘텐츠의 수동 [마이그레이션에](/sharepoint/troubleshoot/migration-tool/content-manual-migration)대한 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-175">To save a document library or list content from a SharePoint Online environment (OneDrive for Business or team sites) to file shares or to a local computer, see [Information about manual migration of SharePoint Online content](/sharepoint/troubleshoot/migration-tool/content-manual-migration).</span></span>

## <a name="transfer-users-data-between-subscriptions"></a><span data-ttu-id="9b3e7-176">구독 간에 사용자 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="9b3e7-176">Transfer users' data between subscriptions</span></span>

### <a name="email"></a><span data-ttu-id="9b3e7-177">메일 주소:</span><span class="sxs-lookup"><span data-stu-id="9b3e7-177">Email:</span></span>

<span data-ttu-id="9b3e7-178">새 구독을 설정한 후 사용자에게 전자 [메일, 연락처,](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) 작업 및 일정 정보를 이동해달고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-178">Ask users to [move their email, contacts, tasks, and calendar information](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) after you set up your new subscription.</span></span> <span data-ttu-id="9b3e7-179">사용자는 초기 사용자 이름(예: sue@contoso.onmicrosoft.com)을 사용하여 이전 전자 메일로 sue@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-179">They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.</span></span>
  
### <a name="onedrive-for-business-data"></a><span data-ttu-id="9b3e7-180">OneDrive 비즈니스용 데이터:</span><span class="sxs-lookup"><span data-stu-id="9b3e7-180">OneDrive For Business data:</span></span>

<span data-ttu-id="9b3e7-181">사용자에게 자신의 컴퓨터에 [](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)비즈니스용 OneDrive 복사/동기화를 요청한 다음 새 구독에 다시 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-181">Ask users to Copy/Sync [OneDrive for Business content to their computer](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd), and then add it back to their new subscription.</span></span>

### <a name="onenote"></a><span data-ttu-id="9b3e7-182">OneNote</span><span class="sxs-lookup"><span data-stu-id="9b3e7-182">OneNote</span></span> 

<span data-ttu-id="9b3e7-183">사용자에게 백업을 [OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) 백업에서 새 구독으로 [메모를](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) 복원하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3e7-183">Ask users to [Back up OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) and to [Restore notes from a backup](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) to their new subscriptions.</span></span>