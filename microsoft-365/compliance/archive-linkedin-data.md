---
title: LinkedIn 데이터를 보관할 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 관리자가 기본 커넥터를 사용하여 LinkedIn 회사 & Microsoft 365로 데이터를 가져오는 방법을 참조하세요.
ms.openlocfilehash: 40e51424d086b0eee42d1f15ea577b7e8f1648c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906148"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a><span data-ttu-id="cfd39-103">LinkedIn 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="cfd39-103">Set up a connector to archive LinkedIn data</span></span>

<span data-ttu-id="cfd39-104">Microsoft 365 규정 준수 센터의 커넥터를 사용하여 LinkedIn 회사 페이지에서 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-104">Use a connector in the Microsoft 365 compliance center to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="cfd39-105">커넥터를 설정하고 구성한 후 24시간마다 한 번씩 특정 LinkedIn Company 페이지의 계정에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-105">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="cfd39-106">커넥터는 회사 페이지에 게시된 메시지를 전자 메일 메시지로 변환한 다음 해당 항목을 Microsoft 365의 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-106">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="cfd39-107">LinkedIn 회사 페이지 데이터가 사서함에 저장되고 나면 소송 보존, 콘텐츠 검색, In-Place 보관, 감사 및 Microsoft 365 보존 정책과 같은 Microsoft 365 규정 준수 기능을 LinkedIn 데이터에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-107">After the LinkedIn Company page data is stored in a mailbox, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="cfd39-108">예를 들어 콘텐츠 검색을 사용하여 이러한 항목을 검색하거나 고급 eDiscovery 사례에서 저장소 사서함을 보관인과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-108">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="cfd39-109">Microsoft 365에서 LinkedIn 데이터를 가져오고 보관하는 커넥터를 만들면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-109">Creating a connector to import and archive LinkedIn data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="cfd39-110">커넥터를 설정하기 전에</span><span class="sxs-lookup"><span data-stu-id="cfd39-110">Before you set up a connector</span></span>

- <span data-ttu-id="cfd39-111">LinkedIn 회사 페이지 커넥터를 만드는 사용자에게 Exchange Online에서 사서함 가져오기 내보내기 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-111">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="cfd39-112">이는 Microsoft 365  규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-112">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="cfd39-113">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-113">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="cfd39-114">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-114">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="cfd39-115">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-115">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="cfd39-116">자세한 내용은 "Exchange [](/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfd39-116">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="cfd39-117">보관할 LinkedIn 회사 페이지의 관리자인 LinkedIn 사용자 계정의 로그인 자격 증명(전자 메일 주소 또는 전화 번호 및 암호)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-117">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="cfd39-118">커넥터를 설정할 때 이러한 자격 증명을 사용하여 LinkedIn에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-118">You use these credentials to sign into LinkedIn when setting up the connector.</span></span>

- <span data-ttu-id="cfd39-119">LinkedIn 커넥터는 하루 총 200,000개 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-119">The LinkedIn connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="cfd39-120">하루 200,000개가 넘는 LinkedIn 항목이 있는 경우 이러한 항목은 Microsoft 365로 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-120">If there are more than 200,000 LinkedIn items in a day, none of those items will be imported to Microsoft 365.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="cfd39-121">LinkedIn 커넥터 만들기</span><span class="sxs-lookup"><span data-stu-id="cfd39-121">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="cfd39-122">으로 <https://compliance.microsoft.com> 이동한 다음 **데이터** 커넥터  >  **LinkedIn 회사 페이지 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfd39-122">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **LinkedIn Company pages**.</span></span>

2. <span data-ttu-id="cfd39-123">**LinkedIn 회사 페이지 제품** 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfd39-123">On the **LinkedIn company pages** product page, click **Add connector**.</span></span>

3. <span data-ttu-id="cfd39-124">서비스 **약관 페이지에서** 수락을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfd39-124">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="cfd39-125">**LinkedIn으로 로그인 페이지에서 LinkedIn으로** **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfd39-125">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="cfd39-126">LinkedIn 로그인 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-126">The LinkedIn sign-in page is displayed.</span></span>

   ![LinkedIn 로그인 페이지](../media/LinkedInSigninPage.png)

5. <span data-ttu-id="cfd39-128">LinkedIn 로그인 페이지에서 보관할 회사 페이지와 연결된 LinkedIn 계정의 전자 메일 주소(또는 전화 번호)와 암호를 입력한 다음 **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfd39-128">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="cfd39-129">로그인한 계정과 연결된 모든 LinkedIn 회사 페이지 목록과 함께 마법사 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-129">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="cfd39-130">커넥터는 한 회사 페이지에만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-130">A connector can only be configured for one company page.</span></span> <span data-ttu-id="cfd39-131">조직에 LinkedIn 회사 페이지가 여러 개 있는 경우 각 페이지에 대한 커넥터를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-131">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![LinkedIn 회사 페이지 목록이 있는 페이지가 표시됩니다.](../media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="cfd39-133">항목을 보관할 회사 페이지를 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfd39-133">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="cfd39-134">저장소 **위치 선택 페이지에서** 상자를 클릭하고 LinkedIn 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 선택한 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cfd39-134">On the **Choose storage location** page, click in the box, select the email address of a Microsoft 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="cfd39-135">항목이 이 사서함의 받은 편지함 폴더로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-135">Items are imported to the inbox folder in this mailbox.</span></span>

8. <span data-ttu-id="cfd39-136">**다음을** 클릭하여 커넥터 설정을 검토한 다음 마친을 클릭하여 커넥터 설정을 완료합니다. </span><span class="sxs-lookup"><span data-stu-id="cfd39-136">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

<span data-ttu-id="cfd39-137">커넥터를 만든 후 데이터 커넥터 페이지로 돌아가 새 커넥터의 가져오기 프로세스 진행률을  볼 수 있습니다(커넥터 목록을 업데이트하는 데 필요한 경우 새로 고침을 선택합니다). </span><span class="sxs-lookup"><span data-stu-id="cfd39-137">After you create the connector, you can go back to the **Data connectors** page to see the progress of the import process for the new connector (select **Refresh** if necessary to update the list of connectors).</span></span> <span data-ttu-id="cfd39-138">상태 **열의 값은** **시작 대기 중입니다.**</span><span class="sxs-lookup"><span data-stu-id="cfd39-138">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="cfd39-139">초기 가져오기 프로세스를 시작하는 데 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-139">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="cfd39-140">커넥터가 처음으로 실행되고 LinkedIn 항목을 가져오면 커넥터가 24시간마다 한 번씩 실행되고 지난 24시간 동안 LinkedIn 회사 페이지에 만들어진 새 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-140">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="cfd39-141">자세한 내용을 확인하려면 데이터 커넥터 페이지의 목록에서 커넥터를 **선택하여** 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-141">To view more details, select the connector in the list on the **Data connectors** page to display the flyout page.</span></span> <span data-ttu-id="cfd39-142">상태 **아래에서** 표시되는 날짜 범위는 커넥터를 만들 때 선택된 기간 필터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-142">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span>

## <a name="more-information"></a><span data-ttu-id="cfd39-143">추가 정보</span><span class="sxs-lookup"><span data-stu-id="cfd39-143">More information</span></span>

<span data-ttu-id="cfd39-144">LinkedIn 항목은 Microsoft 365의 저장소 사서함 받은 편지함에 있는 LinkedIn 하위폴더로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-144">LinkedIn items are imported to the LinkedIn subfolder in the inbox of the storage mailbox in Microsoft 365.</span></span> <span data-ttu-id="cfd39-145">전자 메일 메시지로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfd39-145">They appear as email messages.</span></span>