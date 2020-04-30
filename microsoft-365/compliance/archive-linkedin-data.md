---
title: LinkedIn 데이터를 보관할 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 관리자는 기본 커넥터를 설정 하 여 LinkedIn 회사 페이지에서 Microsoft 365로 데이터를 가져올 수 있습니다. 이를 통해 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 타사 데이터에 대 한 준수를 관리할 수도 있습니다.
ms.openlocfilehash: 6b74e6ba8dca810a8a185ae6011207a419c3e79d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943217"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a><span data-ttu-id="45c2b-104">LinkedIn 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="45c2b-104">Set up a connector to archive LinkedIn data</span></span>

<span data-ttu-id="45c2b-105">Microsoft 365 준수 센터의 커넥터를 사용 하 여 LinkedIn 회사 페이지에서 데이터를 가져오고 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-105">Use a connector in the Microsoft 365 compliance center to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="45c2b-106">커넥터를 설정 하 고 구성한 후에는 24 시간 마다 한 번씩 특정 LinkedIn 회사 페이지의 계정에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-106">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="45c2b-107">이 커넥터는 회사 페이지에 게시 된 메시지를 전자 메일 메시지로 변환한 다음 해당 항목을 Microsoft 365의 사서함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-107">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="45c2b-108">LinkedIn 회사 페이지 데이터가 사서함에 저장 되 면 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사 및 Microsoft 365 고정 정책과 같은 Microsoft 365 준수 기능을 LinkedIn 데이터에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-108">After the LinkedIn Company page data is stored in a mailbox, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="45c2b-109">예를 들어 콘텐츠 검색을 사용 하 여 이러한 항목을 검색 하거나, 고급 eDiscovery 사례의 custodian에 저장소 사서함을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-109">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="45c2b-110">Microsoft 365에서 LinkedIn 데이터를 가져오고 보관 하기 위한 커넥터를 만들면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-110">Creating a connector to import and archive LinkedIn data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you--begin"></a><span data-ttu-id="45c2b-111">시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="45c2b-111">Before you  begin</span></span>

- <span data-ttu-id="45c2b-112">조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-112">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="45c2b-113">이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 Microsoft 365 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-113">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Microsoft 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="45c2b-114">LinkedIn 회사 페이지 커넥터를 만드는 사용자에 게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-114">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="45c2b-115">이는 Microsoft 365 준수 센터의 **데이터 커넥터** 페이지에서 커넥터를 추가 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-115">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="45c2b-116">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-116">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="45c2b-117">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-117">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="45c2b-118">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-118">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="45c2b-119">자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45c2b-119">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="45c2b-120">보관 하려는 LinkedIn 회사 페이지의 관리자 인 LinkedIn 사용자 계정의 로그인 자격 증명 (전자 메일 주소 또는 전화 번호와 암호)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-120">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="45c2b-121">커넥터를 설정할 때 이러한 자격 증명을 사용 하 여 LinkedIn에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-121">You use these credentials to sign in to LinkedIn when setting up the connector.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="45c2b-122">LinkedIn 커넥터 만들기</span><span class="sxs-lookup"><span data-stu-id="45c2b-122">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="45c2b-123">로 이동한 <https://compliance.microsoft.com> 후 **데이터 커넥터** > **LinkedIn 회사 페이지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-123">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **LinkedIn Company pages**.</span></span>

2. <span data-ttu-id="45c2b-124">**LinkedIn 회사 페이지** 제품 페이지에서 **커넥터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-124">On the **LinkedIn company pages** product page, click **Add connector**.</span></span>

3. <span data-ttu-id="45c2b-125">**서비스 약관** 페이지에서 **수락**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-125">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="45c2b-126">LinkedIn을 **사용** 하 여 로그인 페이지에서 **Linkedin과 함께 로그인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-126">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="45c2b-127">LinkedIn 로그인 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-127">The LinkedIn sign in page is displayed.</span></span>

   ![LinkedIn 로그인 페이지](../media/LinkedInSigninPage.png)

5. <span data-ttu-id="45c2b-129">LinkedIn 로그인 페이지에서 보관 하려는 회사 페이지와 연결 된 LinkedIn 계정의 전자 메일 주소 (또는 전화 번호)와 암호를 입력 하 고 **로그인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-129">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="45c2b-130">로그인 한 계정에 연결 된 모든 LinkedIn 회사 페이지 목록과 함께 마법사 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-130">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="45c2b-131">커넥터는 한 회사 페이지에 대해서만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-131">A connector can only be configured for one company page.</span></span> <span data-ttu-id="45c2b-132">조직에 LinkedIn 회사 페이지가 여러 개 있는 경우 각 페이지에 대 한 커넥터를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-132">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![LinkedIn 회사 페이지 목록이 있는 페이지가 표시 됨](../media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="45c2b-134">항목을 보관 하려는 회사 페이지를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-134">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="45c2b-135">**필터 설정** 페이지에서 특정 기간에 해당 하는 항목을 처음 가져올 때 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-135">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="45c2b-136">보존 기간을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-136">Select an age, and then click **Next**.</span></span>

8. <span data-ttu-id="45c2b-137">**저장 위치 선택** 페이지에서 상자를 클릭 하 고 LinkedIn 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 선택한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-137">On the **Choose storage location** page, click in the box, select the email address of an Microsoft 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="45c2b-138">이 사서함의 받은 편지함 폴더로 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-138">Items are imported to the inbox folder in this mailbox.</span></span>

9. <span data-ttu-id="45c2b-139">**관리자 동의 제공**에서 **동의 제공** 을 클릭 한 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-139">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="45c2b-140">조직의 데이터에 액세스 하려면 Office 365 가져오기 서비스에 대 한 동의를 제공 하는 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-140">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

10. <span data-ttu-id="45c2b-141">**다음** 을 클릭 하 여 커넥터 설정을 검토 한 다음 **마침을** 클릭 하 여 커넥터 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-141">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

<span data-ttu-id="45c2b-142">커넥터를 만든 후에는 **데이터 커넥터** 페이지로 돌아가 새 커넥터에 대 한 가져오기 프로세스 진행 상황을 확인할 수 있습니다 (커넥터 목록 업데이트를 위해 필요한 경우 **새로 고침** 선택).</span><span class="sxs-lookup"><span data-stu-id="45c2b-142">After you create the connector, you can go back to the **Data connectors** page to see the progress of the import process for the new connector (select **Refresh** if necessary to update the list of connectors).</span></span> <span data-ttu-id="45c2b-143">**상태** 열의 값이 **시작을 기다리는 중**입니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-143">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="45c2b-144">초기 가져오기 프로세스를 시작 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-144">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="45c2b-145">처음에 커넥터를 실행 하 고 LinkedIn 항목을 가져온 후에는 24 시간 마다 한 번씩 커넥터가 실행 되 고 이전 24 시간 동안 LinkedIn 회사 페이지에서 만든 모든 새 항목이 가져오기 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-145">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="45c2b-146">자세한 내용을 보려면 **데이터 커넥터** 페이지의 목록에서 커넥터를 선택 하 여 플라이 아웃 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-146">To view more details, select the connector in the list on the **Data connectors** page to display the flyout page.</span></span> <span data-ttu-id="45c2b-147">**상태**에서 표시 되는 날짜 범위는 커넥터를 만들 때 선택한 연령 필터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-147">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span> 

## <a name="more-information"></a><span data-ttu-id="45c2b-148">추가 정보</span><span class="sxs-lookup"><span data-stu-id="45c2b-148">More information</span></span>

<span data-ttu-id="45c2b-149">LinkedIn 항목은 Microsoft 365에서 저장소 사서함의 받은 편지함에 있는 LinkedIn 하위 폴더로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-149">LinkedIn items are imported to the LinkedIn subfolder in the inbox of the storage mailbox in Microsoft 365.</span></span> <span data-ttu-id="45c2b-150">전자 메일 메시지로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="45c2b-150">They appear as email messages.</span></span>
