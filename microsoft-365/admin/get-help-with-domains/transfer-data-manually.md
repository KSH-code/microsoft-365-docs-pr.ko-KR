---
title: 두 계정 간에 데이터를 수동으로 전송
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 계획 또는 회사 이름을 변경 했을 때 두 Microsoft 365 계정 간에 데이터를 수동으로 전송 하거나 여러 구독을 하나로 결합 하는 방법을 알아봅니다.
ms.openlocfilehash: c0cb6531518c18e8cdc5b5829dc05a5b9b375291
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628378"
---
# <a name="transfer-data-manually-between-two-accounts"></a><span data-ttu-id="44e0f-103">두 계정 간에 데이터를 수동으로 전송</span><span class="sxs-lookup"><span data-stu-id="44e0f-103">Transfer data manually between two accounts</span></span>

<span data-ttu-id="44e0f-104">Sleeves을 롤업 하 고 일정에서 시간을 차단: 두 Microsoft 365 계정 간에 데이터를 전송 하는 것은 수동, 복잡 및 시간이 많이 걸리는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-104">Prepare to roll up your sleeves and block out a chunk of time on your calendar: transferring data between two Microsoft 365 accounts is a manual, complicated, and time-consuming process.</span></span> <span data-ttu-id="44e0f-105">자동 또는 지원 되는 프로세스가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-105">This is not an automated or supported process.</span></span> <span data-ttu-id="44e0f-106">시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-106">We'll get you started.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="44e0f-107">전자 메일, 비즈니스용 Skype 및 Microsoft 365에서 호스트 되는 공개 웹 사이트가 작동 하는 동안 문제가 발생 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-107">There will be down time during the process where email, Skype for Business and a public website hosted on Microsoft 365 won't work.</span></span> <span data-ttu-id="44e0f-108">사용자는 새 사용자 이름과 암호를 얻게 되며 Outlook을 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-108">Users will get new user names and passwords, and they'll need to reset up Outlook.</span></span>

<span data-ttu-id="44e0f-109">**다음 중 하나가 적용 될 경우이 항목의 지침을 사용 하 여 데이터를 수동으로 전송 하기만 하면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="44e0f-109">**Only transfer data manually using the instructions in this topic if one of the following applies:**</span></span>
  
- <span data-ttu-id="44e0f-110">다른 서비스 제품군의 요금제로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-110">You need to change to a plan in a different service family.</span></span>

- <span data-ttu-id="44e0f-111">회사 이름이 변경 되었으며, 다른 초기 도메인 이름을 사용 하기 때문에 새 구독을 만들고 데이터를 마이그레이션하기를 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-111">Your company name changed, and you decided to create a new subscription and migrate your data because you want to use different initial domain names.</span></span>

- <span data-ttu-id="44e0f-112">여러 구독을 하나의 새 구독과 결합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-112">You need to combine multiple subscriptions into one new one.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44e0f-113">[구독 계획을 변경](../../commerce/subscriptions/switch-to-a-different-plan.md) 해야 하 고 요금제 전환 마법사를 사용할 수 있는 경우 또는 요금제 전환 마법사가 작동 하지 않더라도 동일한 구독 패밀리에서 새 구독 계획으로 전송 해야 하는 경우에는 데이터를 수동으로 전송할 필요가 없으며,이 경우에는 가동 중지 시간이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-113">If you need to [change your subscription plan](../../commerce/subscriptions/switch-to-a-different-plan.md) and can use the Switch plans wizard, or if you need to transfer to a new subscription plan in the same subscription family even when the Switch plans wizard doesn't work, you don't need to manually transfer your data, and there is no down time.</span></span>

|<span data-ttu-id="44e0f-114">**Tasks**</span><span class="sxs-lookup"><span data-stu-id="44e0f-114">**Tasks**</span></span>|<span data-ttu-id="44e0f-115">**Steps**</span><span class="sxs-lookup"><span data-stu-id="44e0f-115">**Steps**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44e0f-116">이동 하려는 계획을 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-116">Purchase the plan you want to move to.</span></span>  <br/> |<span data-ttu-id="44e0f-117">등록할 때 초기 도메인 이름에 사용할 회사 *이름 (예: onmicrosoft.com* , public.sharepoint.com 및 *sharepoint.com)을* 지정 *합니다.*</span><span class="sxs-lookup"><span data-stu-id="44e0f-117">When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com.</span></span> <span data-ttu-id="44e0f-118">기존 구독에 사용한 것과는 다른 *회사* 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-118">You need to use a different  *yourcompany*  name than you did for any existing subscriptions.</span></span>  <br/> <span data-ttu-id="44e0f-119">> [!NOTE]>은 일반적으로 구독을 취소 한 후 몇 개월 동안 시스템에서 해당 *회사* 를 사용 하는 초기 도메인 이름을 해제 하는 데 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-119">> [!NOTE]>  It typically takes a minimum of several months after cancelling a subscription to release the initial domain names that use  *yourcompany*  from our systems.</span></span> <span data-ttu-id="44e0f-120">이전 Microsoft 365 구독의 모든 데이터를 저장 하 고 해당 구독을 취소 하더라도 새 구독에서 이전 *회사* 가치를 즉시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-120">Even if you plan to save all your data from your old Microsoft 365 subscription, and cancel that subscription, the old  *yourcompany*  value is not immediately available for use in a new subscription.</span></span>           |
|<span data-ttu-id="44e0f-121">이전 Microsoft 365 구독에서 사용자 지정 도메인을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-121">Remove your custom domain from your old Microsoft 365 subscription.</span></span>  <br/> | <span data-ttu-id="44e0f-122">[도메인을 제거 하기 전에 필요한 단계](remove-a-domain.md) 에 따라 사용자 전자 메일 주소에서 도메인 이름을 제거 하 고 사용자 지정 도메인에 대 한 전자 메일 및 LYNC 용 DNS 레코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-122">Follow the [required steps before you remove a domain](remove-a-domain.md) to remove the domain name from user email addresses and remove DNS records for email and Lync for the custom domain.</span></span> <span data-ttu-id="44e0f-123">Microsoft 365에서 공개 웹 사이트를 호스트 하는 경우에는이를 가리키는 CNAME 레코드도 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-123">If you host your public website on Microsoft 365, you'll also need to remove the CNAME record that points to it.</span></span>  <br/> <span data-ttu-id="44e0f-124">> [!IMPORTANT]>이 사용자 지정 도메인으로 전자 메일을 라우팅하는 MX 레코드를 제거한 후 새 계정에 도메인을 추가 하 고 새 MX 레코드를 설정 하 고 사용자를 설정할 때까지 전자 메일이 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-124">> [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users.</span></span> <span data-ttu-id="44e0f-125">Lync에 대 한 DNS 레코드를 제거 하면 Lync가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-125">When you remove the DNS records for Lync, Lync will stop working.</span></span> <span data-ttu-id="44e0f-126">또한 공개 웹 사이트를 가리키는 CNAME 레코드를 제거한 후에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-126">And after you remove the CNAME record that points to your public website, it will not be available.</span></span>           <span data-ttu-id="44e0f-127">[도메인을 제거](remove-a-domain.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-127">[Remove the domain](remove-a-domain.md) .</span></span>  <br/> |
|<span data-ttu-id="44e0f-128">새 구독에 대 한 사용자 지정 도메인을 설정 하 고 사용자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-128">Set up your custom domain for your new subscription, and set up your users.</span></span>  <br/> | <span data-ttu-id="44e0f-129">사용자 지정 도메인에 필요한 DNS 레코드를 만드는 작업을 포함 하 여 새 구독을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-129">Set up your new subscription, including creating the required DNS records for your custom domain.</span></span>  <br/>  <span data-ttu-id="44e0f-130">사용자 지정 도메인에 전자 메일 주소를 사용 하 여 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-130">Create your users, with email addresses on your custom domain.</span></span>  <br/> |
|<span data-ttu-id="44e0f-131">이전 구독에서 새 구독으로 데이터를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-131">Transfer data from your old subscription to your new subscription.</span></span>  <br/> | <span data-ttu-id="44e0f-132">별도의 브라우저 창에서 두 계정에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-132">Sign in to both accounts in separate browser windows:</span></span>  <br/>  <span data-ttu-id="44e0f-133">Internet Explorer 아이콘을 마우스 오른쪽 단추로 클릭 하 고 두 개의 InPrivate 브라우저 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-133">Right-click the Internet Explorer icon, and open two InPrivate browser windows.</span></span> <span data-ttu-id="44e0f-134">두 windows에서 다른 자격 증명을 사용 하 여 두 계정 모두에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-134">You can use different credentials in the two windows to sign in on both accounts.</span></span>  <br/> [<span data-ttu-id="44e0f-135">구독 간 관리 설정 전송</span><span class="sxs-lookup"><span data-stu-id="44e0f-135">Transfer administrative settings between subscriptions</span></span>](#email) <br/> [<span data-ttu-id="44e0f-136">팀 사이트 구조 및 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="44e0f-136">Transfer team site structure and data</span></span>](#transfer-team-site-structure-and-data) <br/> [<span data-ttu-id="44e0f-137">구독 간 공용 웹 사이트 전송</span><span class="sxs-lookup"><span data-stu-id="44e0f-137">Transfer a public website between subscriptions</span></span>](#transfer-a-public-website-between-subscriptions) <br/> [<span data-ttu-id="44e0f-138">구독 간 관리 설정 전송</span><span class="sxs-lookup"><span data-stu-id="44e0f-138">Transfer administrative settings between subscriptions</span></span>](#email) <br/> |
|<span data-ttu-id="44e0f-139">Microsoft 365에 대 한 Microsoft 지원 서비스를 호출 하 여 완료 한 계획에 대 한 구독을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-139">Cancel the subscription for the plan you're done with by calling Microsoft Support for Microsoft 365.</span></span>  <br/> | <span data-ttu-id="44e0f-140">새 구독이 작동 하며 모든 데이터가 전송 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-140">Verify that your new subscription is working and all data has been transferred.</span></span>  <br/>  <span data-ttu-id="44e0f-141">[고객 지원에 문의](../contact-support-for-business-products.md) 하 여 이전 구독을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-141">[Contact customer support](../contact-support-for-business-products.md) to cancel your old subscription.</span></span>  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a><span data-ttu-id="44e0f-142">구독 간 관리 설정 전송</span><span class="sxs-lookup"><span data-stu-id="44e0f-142">Transfer administrative settings between subscriptions</span></span>

<span data-ttu-id="44e0f-143">각 계정의 다음 페이지로 이동 하 여 이전 계정의 설정을 기반으로 새 계정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-143">Go to the following pages on each account, and set up the new account based on the old account's settings.</span></span>
  
<span data-ttu-id="44e0f-144">Microsoft 365에서 Microsoft 365 중소 Business 또는 Microsoft 365 Enterprise로 데이터를 전송 하는 경우 관리 페이지는 서로 다른 방식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-144">If you are transferring data from Microsoft 365 to Microsoft 365 Midsize Business or Microsoft 365 Enterprise, the admin pages are structured differently.</span></span> <span data-ttu-id="44e0f-145">비디오 시청 [: Microsoft 365 Enterprise를 소개](https://support.office.com/article/11f7b4a0-1294-4e94-9238-beaae26efa9c.aspx)하 고 다음 위치로 이동 하 여 관리 설정을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="44e0f-145">Watch a [Video: Introducing Microsoft 365 Enterprise](https://support.office.com/article/11f7b4a0-1294-4e94-9238-beaae26efa9c.aspx), and go to the following places to look at admin settings.</span></span>
  
<span data-ttu-id="44e0f-146">Microsoft 365 Enterprise 및 Microsoft 365 중소 Business:</span><span class="sxs-lookup"><span data-stu-id="44e0f-146">For Microsoft 365 Enterprise and Microsoft 365 Midsize Business:</span></span>
  
|<span data-ttu-id="44e0f-147">**위치**</span><span class="sxs-lookup"><span data-stu-id="44e0f-147">**Location**</span></span>|<span data-ttu-id="44e0f-148">**용도**</span><span class="sxs-lookup"><span data-stu-id="44e0f-148">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44e0f-149">**관리** \> **Microsoft 365** \> **서비스 설정**</span><span class="sxs-lookup"><span data-stu-id="44e0f-149">**Admin** \> **Microsoft 365** \> **Service settings**</span></span> <br/> |<span data-ttu-id="44e0f-150">메일, 사이트, Lync, 사용자 소프트웨어, 암호, 커뮤니티, 권한 관리 및 모바일의 설정에 대 한 각 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-150">Select each tab for settings for mail, sites, Lync, user software, passwords, community, rights management, and mobile.</span></span>  <br/> |
|<span data-ttu-id="44e0f-151">**관리** \> **Exchange**</span><span class="sxs-lookup"><span data-stu-id="44e0f-151">**Admin** \> **Exchange**</span></span> <br/> | <span data-ttu-id="44e0f-152">Exchange Online 설정</span><span class="sxs-lookup"><span data-stu-id="44e0f-152">Exchange Online settings</span></span>  <br/> |
|<span data-ttu-id="44e0f-153">**관리** \> **SharePoint**</span><span class="sxs-lookup"><span data-stu-id="44e0f-153">**Admin** \> **SharePoint**</span></span> <br/> | <span data-ttu-id="44e0f-154">SharePoint Online 설정</span><span class="sxs-lookup"><span data-stu-id="44e0f-154">SharePoint Online settings</span></span>  <br/> |
|<span data-ttu-id="44e0f-155">**Admin** \> **비즈니스용 Skype** 관리자</span><span class="sxs-lookup"><span data-stu-id="44e0f-155">**Admin** \> **Skype for Business**</span></span> <br/> |<span data-ttu-id="44e0f-156">추가 비즈니스용 Skype 설정</span><span class="sxs-lookup"><span data-stu-id="44e0f-156">Additional Skype for Business settings</span></span>  <br/> |

<span data-ttu-id="44e0f-157">Microsoft 365 Small Business</span><span class="sxs-lookup"><span data-stu-id="44e0f-157">For Microsoft 365 Small Business</span></span>
  
|<span data-ttu-id="44e0f-158">**위치**</span><span class="sxs-lookup"><span data-stu-id="44e0f-158">**Location**</span></span>|<span data-ttu-id="44e0f-159">**용도**</span><span class="sxs-lookup"><span data-stu-id="44e0f-159">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44e0f-160">\> **관리** **조직 차원의 설정 관리**</span><span class="sxs-lookup"><span data-stu-id="44e0f-160">**Admin** \> **Manage organization-wide settings**</span></span> <br/> |<span data-ttu-id="44e0f-161">관리 설정</span><span class="sxs-lookup"><span data-stu-id="44e0f-161">Administrative settings</span></span>  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a><span data-ttu-id="44e0f-162">구독 간 공용 웹 사이트 전송</span><span class="sxs-lookup"><span data-stu-id="44e0f-162">Transfer a public website between subscriptions</span></span>

<span data-ttu-id="44e0f-163">Microsoft 365에서 호스트 되는 공개 웹 사이트가 있는 경우이를 저장 하 고 새 구독에 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-163">If you have a public website hosted on Microsoft 365, you need to save it and re-create it on your new subscription.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44e0f-164">공용 웹 사이트가 DNS 호스팅 공급자에 호스트 되는 경우에는 변경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-164">If your public website is hosted at a DNS hosting provider, no changes are required.</span></span> <span data-ttu-id="44e0f-165">전환의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-165">It will not be affected by your transition.</span></span>
  
<span data-ttu-id="44e0f-166">문서 라이브러리 또는 목록 콘텐츠를 SharePoint Online 환경에서 파일 공유 또는 로컬 컴퓨터로 저장 하려면 [Sharepoint online 콘텐츠 수동 마이그레이션을](https://go.microsoft.com/fwlink/p/?LinkId=402910)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44e0f-166">To save a document library or list content from a SharePoint Online environment to file shares or to a local computer, see [Manual migration of SharePoint Online content](https://go.microsoft.com/fwlink/p/?LinkId=402910).</span></span>
  
> [!NOTE]
> <span data-ttu-id="44e0f-167">공용 사이트 마이그레이션 앱에서 데이터를 다른 구독으로 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-167">The Public site migration app can't transfer data to a different subscription.</span></span>
  
## <a name="transfer-team-site-structure-and-data"></a><span data-ttu-id="44e0f-168">팀 사이트 구조 및 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="44e0f-168">Transfer team site structure and data</span></span>

<span data-ttu-id="44e0f-169">팀 사이트 데이터를 저장 하거나 전송 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-169">There are several ways to save or transfer team site data:</span></span>
  
- <span data-ttu-id="44e0f-170">이전 사이트를 서식 파일로 저장 하 고 서식 파일을 새 사이트로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-170">You can save the old site as a template and import the template into the new site.</span></span>

- <span data-ttu-id="44e0f-171">문서를 전송 하려면 먼저 새 사이트에서 계층 구조를 수동으로 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-171">To transfer documents, first manually recreate your hierarchy on the new site.</span></span> <span data-ttu-id="44e0f-172">그런 다음 두 SharePoint 팀 사이트를 동시에 열고 Windows 탐색기를 사용 하 여 두 문서 라이브러리를 열고 문서를 복사 하 여 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-172">Then you can open both SharePoint team sites at the same time, open both document libraries with Windows Explorer, and copy and paste the documents.</span></span> <span data-ttu-id="44e0f-173">[비디오: Explorer에서 열기를 사용 하 여 라이브러리 파일 복사 또는 이동을](https://support.office.com/article/c27bc6f3-7b38-4c29-b947-5d00c7153384.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44e0f-173">See [Video: Copy or move library files by using Open with Explorer](https://support.office.com/article/c27bc6f3-7b38-4c29-b947-5d00c7153384.aspx).</span></span>

- <span data-ttu-id="44e0f-174">목록 데이터를 전송 하려면 [목록 서식 파일](https://support.office.com/article/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393.aspx)을 저장 하 고 저장 된 서식 파일을 사용 하 여 새 사이트에 목록을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-174">To transfer list data, save a [list template](https://support.office.com/article/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393.aspx), and use the saved template to re-create the list on the new site.</span></span>

- <span data-ttu-id="44e0f-175">SharePoint Online 환경 (비즈니스용 OneDrive 또는 팀 사이트)의 문서 라이브러리 또는 목록 콘텐츠를 파일 공유 또는 로컬 컴퓨터에 저장 하려면 [Sharepoint online 콘텐츠의 수동 마이그레이션에 대 한 정보](https://support.microsoft.com/kb/2783484)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44e0f-175">To save a document library or list content from a SharePoint Online environment (OneDrive for Business or team sites) to file shares or to a local computer, see [Information about manual migration of SharePoint Online content](https://support.microsoft.com/kb/2783484).</span></span>

## <a name="transfer-users-data-between-subscriptions"></a><span data-ttu-id="44e0f-176">구독 간 사용자 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="44e0f-176">Transfer users' data between subscriptions</span></span>

### <a name="email"></a><span data-ttu-id="44e0f-177">메일 주소:</span><span class="sxs-lookup"><span data-stu-id="44e0f-177">Email:</span></span>

<span data-ttu-id="44e0f-178">새 구독을 설정한 후 사용자에 게 [전자 메일, 연락처, 작업 및 일정 정보를 이동](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx) 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-178">Ask users to [move their email, contacts, tasks, and calendar information](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx) after you set up your new subscription.</span></span> <span data-ttu-id="44e0f-179">Sue@contoso.onmicrosoft.com와 같은 초기 사용자 이름을 사용 하 여 이전 전자 메일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-179">They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.</span></span>
  
### <a name="onedrive-for-business-data"></a><span data-ttu-id="44e0f-180">비즈니스용 OneDrive 데이터:</span><span class="sxs-lookup"><span data-stu-id="44e0f-180">OneDrive For Business data:</span></span>

<span data-ttu-id="44e0f-181">사용자에 게 [비즈니스용 OneDrive 콘텐츠를 컴퓨터에](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)복사/동기화 하도록 요청 하 고 새 구독에 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e0f-181">Ask users to Copy/Sync [OneDrive for Business content to their computer](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx), and then add it back to their new subscription.</span></span>
