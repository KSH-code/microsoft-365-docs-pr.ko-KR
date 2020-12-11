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
description: 관리자가 네이티브 커넥터를 사용하여 LinkedIn 회사 & Microsoft 365로 데이터를 가져오는 데 사용할 수 있는 설정을 설정하는 방법에 대해 자세히 알아보십시오.
ms.openlocfilehash: 42183be3663fbf4b55eadde2173b492feeae5373
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619984"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a><span data-ttu-id="f4617-103">LinkedIn 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="f4617-103">Set up a connector to archive LinkedIn data</span></span>

<span data-ttu-id="f4617-104">Microsoft 365 규정 준수 센터의 커넥터를 사용하여 LinkedIn 회사 페이지에서 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-104">Use a connector in the Microsoft 365 compliance center to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="f4617-105">커넥터를 설정하고 구성한 후 24시간마다 한 번씩 특정 LinkedIn Company 페이지의 계정에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-105">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="f4617-106">커넥터는 회사 페이지에 게시된 메시지를 전자 메일 메시지로 변환한 다음 해당 항목을 Microsoft 365의 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-106">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="f4617-107">LinkedIn 회사 페이지 데이터가 사서함에 저장되고 나면 소송 보존, 콘텐츠 검색, In-Place 보관, 감사 및 Microsoft 365 보존 정책과 같은 Microsoft 365 규정 준수 기능을 LinkedIn 데이터에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-107">After the LinkedIn Company page data is stored in a mailbox, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="f4617-108">예를 들어 콘텐츠 검색을 사용하여 이러한 항목을 검색하거나 고급 eDiscovery 사례에서 저장소 사서함을 보관인과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-108">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="f4617-109">Microsoft 365에서 LinkedIn 데이터를 가져오고 보관하는 커넥터를 만들면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-109">Creating a connector to import and archive LinkedIn data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="assign-roles-and-verify-credentials"></a><span data-ttu-id="f4617-110">역할을 할당하고 자격 증명 확인</span><span class="sxs-lookup"><span data-stu-id="f4617-110">Assign roles, and verify credentials</span></span>

- <span data-ttu-id="f4617-111">LinkedIn 회사 페이지 커넥터를 만드는 사용자에게 Exchange Online에서 사서함 가져오기 내보내기 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-111">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="f4617-112">이는 Microsoft 365 규정 준수 센터의 **데이터** 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-112">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f4617-113">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-113">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="f4617-114">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-114">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="f4617-115">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-115">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="f4617-116">자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서에서 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f4617-116">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="f4617-117">보관할 LinkedIn 회사 페이지의 관리자인 LinkedIn 사용자 계정의 로그인 자격 증명(전자 메일 주소 또는 전화 번호 및 암호)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-117">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="f4617-118">커넥터를 설정할 때 이러한 자격 증명을 사용하여 LinkedIn에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-118">You use these credentials to sign into LinkedIn when setting up the connector.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="f4617-119">LinkedIn 커넥터 만들기</span><span class="sxs-lookup"><span data-stu-id="f4617-119">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="f4617-120">Go to <https://compliance.microsoft.com> and then click Data **connectors**  >  **LinkedIn Company pages.**</span><span class="sxs-lookup"><span data-stu-id="f4617-120">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **LinkedIn Company pages**.</span></span>

2. <span data-ttu-id="f4617-121">**LinkedIn 회사 페이지** 제품 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f4617-121">On the **LinkedIn company pages** product page, click **Add connector**.</span></span>

3. <span data-ttu-id="f4617-122">서비스 약관 **페이지에서** 수락을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f4617-122">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="f4617-123">**LinkedIn으로 로그인 페이지에서 LinkedIn으로** **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f4617-123">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="f4617-124">LinkedIn 로그인 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-124">The LinkedIn sign-in page is displayed.</span></span>

   ![LinkedIn 로그인 페이지](../media/LinkedInSigninPage.png)

5. <span data-ttu-id="f4617-126">LinkedIn 로그인 페이지에서 보관할 회사 페이지와 연결된 LinkedIn 계정의 전자 메일 주소(또는 전화 번호) 및 암호를 입력한 다음 **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f4617-126">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="f4617-127">로그인한 계정과 연결된 모든 LinkedIn 회사 페이지 목록이 마법사 페이지와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-127">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="f4617-128">커넥터는 한 회사 페이지에만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-128">A connector can only be configured for one company page.</span></span> <span data-ttu-id="f4617-129">조직에 LinkedIn 회사 페이지가 여러 개 있는 경우 각 페이지에 대한 커넥터를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-129">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![LinkedIn 회사 페이지 목록이 있는 페이지가 표시됩니다.](../media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="f4617-131">항목을 보관할 회사 페이지를 선택하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f4617-131">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="f4617-132">저장소 **위치** 선택 페이지에서 상자를 클릭하고 LinkedIn 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 선택하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f4617-132">On the **Choose storage location** page, click in the box, select the email address of a Microsoft 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="f4617-133">항목이 이 사서함의 받은 편지함 폴더로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-133">Items are imported to the inbox folder in this mailbox.</span></span>

8. <span data-ttu-id="f4617-134">**다음을** 클릭하여 커넥터 설정을 검토한 다음 **마친을** 클릭하여 커넥터 설정을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-134">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

<span data-ttu-id="f4617-135">커넥터를 만든 후 데이터 커넥터 페이지로 돌아가 새 커넥터의 가져오기 프로세스 진행률을  볼 수 있습니다(필요한 경우 새로 고침을 선택하여 커넥터 목록을 업데이트합니다). </span><span class="sxs-lookup"><span data-stu-id="f4617-135">After you create the connector, you can go back to the **Data connectors** page to see the progress of the import process for the new connector (select **Refresh** if necessary to update the list of connectors).</span></span> <span data-ttu-id="f4617-136">상태 **열의 값이** 시작 **대기 중입니다.**</span><span class="sxs-lookup"><span data-stu-id="f4617-136">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="f4617-137">초기 가져오기 프로세스를 시작하는 데 최대 24시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-137">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="f4617-138">커넥터가 처음으로 실행되고 LinkedIn 항목을 가져온 후 커넥터는 24시간마다 한 번씩 실행되고 지난 24시간 동안 LinkedIn 회사 페이지에 만들어진 새 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-138">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="f4617-139">자세한 내용을 확인하려면 데이터 커넥터 페이지의 목록에서 커넥터를 선택하여 플라이아웃 페이지를 표시합니다. </span><span class="sxs-lookup"><span data-stu-id="f4617-139">To view more details, select the connector in the list on the **Data connectors** page to display the flyout page.</span></span> <span data-ttu-id="f4617-140">상태 **아래에서** 표시되는 날짜 범위는 커넥터를 만들 때 선택된 기간 필터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-140">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span>

## <a name="more-information"></a><span data-ttu-id="f4617-141">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f4617-141">More information</span></span>

<span data-ttu-id="f4617-142">LinkedIn 항목은 Microsoft 365의 저장소 사서함 받은 편지함에 있는 LinkedIn 하위폴더로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-142">LinkedIn items are imported to the LinkedIn subfolder in the inbox of the storage mailbox in Microsoft 365.</span></span> <span data-ttu-id="f4617-143">전자 메일 메시지로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4617-143">They appear as email messages.</span></span>
