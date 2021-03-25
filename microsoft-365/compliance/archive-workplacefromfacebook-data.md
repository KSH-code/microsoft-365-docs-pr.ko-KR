---
title: Microsoft 365에서 Facebook 데이터에서 Workplace를 보관하는 커넥터 설정
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
ms.collection: M365-security-compliance
description: 관리자는 Veritas의 Merge1 사이트에 보관된 Facebook의 Workplace에서 Microsoft 365로 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 커넥터를 설정하려면 Veritas와 함께 작업해야 합니다. 이 커넥터를 사용하면 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 25221b1d71fe106f0f6dcf9c629414aeb0de8709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163832"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a><span data-ttu-id="4e753-104">Facebook 데이터에서 Workplace를 보관하는 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="4e753-104">Set up a connector to archive Workplace from Facebook data</span></span>

<span data-ttu-id="4e753-105">Microsoft 365 규정 준수 센터의 Veritas 커넥터를 사용하여 Facebook에서 Microsoft 365 조직의 사용자 사서함으로 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from Workplace from Facebook to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="4e753-106">Veritas는 타사 데이터 원본에서 항목을 캡처하고(정기적으로) 해당 항목을 Microsoft 365로 가져오도록 구성된 Facebook 커넥터에서 [Workplace를](https://globanet.com/workplace/) 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-106">Veritas provides a [Workplace from Facebook](https://globanet.com/workplace/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="4e753-107">커넥터는 채팅, 첨부 파일, 게시물, 비디오 등의 콘텐츠를 Workplace에서 전자 메일 메시지 형식으로 변환한 다음 이러한 항목을 Microsoft 365의 사용자 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-107">The connector converts the content such as chats, attachments, posts, and videos from Workplace to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="4e753-108">Workplace 데이터를 사용자 사서함에 저장한 후 소송 보존, eDiscovery, 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-108">After Workplace data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="4e753-109">Facebook 커넥터에서 Workplace를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-109">Using Workplace from Facebook connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-workplace-from-facebook-data"></a><span data-ttu-id="4e753-110">Facebook 데이터에서 작업 공간 보관 개요</span><span class="sxs-lookup"><span data-stu-id="4e753-110">Overview of archiving Workplace from Facebook data</span></span>

<span data-ttu-id="4e753-111">다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 Workplace 데이터를 보관하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-111">The following overview explains the process of using a connector to archive Workplace data in Microsoft 365.</span></span>

![Facebook 데이터에서 Workplace용 보관 워크플로](../media/WorkplaceConnectorWorkflow.png)

1. <span data-ttu-id="4e753-113">조직은 Facebook의 Workplace와 함께 작업하여 Workplace 사이트를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-113">Your organization works with Workplace from Facebook to set up and configure a Workplace site.</span></span>

2. <span data-ttu-id="4e753-114">24시간마다 Workplace의 항목이 Veritas Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-114">Once every 24 hours, items from Workplace are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="4e753-115">또한 커넥터는 이러한 항목의 내용을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-115">The connector also converts the content of these items to an email message format.</span></span>

3. <span data-ttu-id="4e753-116">Microsoft 365 규정 준수 센터에서 만든 Facebook 커넥터에서 Workplace를 매일 Veritas Merge1에 연결하고, Workplace 항목을 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-116">The Workplace from Facebook connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 every day, and transfers the Workplace items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="4e753-117">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 항목을 특정 사용자의 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-117">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="4e753-118">Facebook의 받은 편지함 폴더에 **Workplace라는** 하위 폴더가 만들어지며 Workplace 항목을 해당 폴더로 가져오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-118">A subfolder in the Inbox folder named **Workplace from Facebook** is created, and the Workplace items are imported to that folder.</span></span> <span data-ttu-id="4e753-119">이 커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="4e753-120">모든 Workplace 항목에는 모든 채팅 또는 사후 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-120">Every Workplace item contains this property, which is populated with the email address of every chat or post participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4e753-121">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="4e753-121">Before you begin</span></span>

- <span data-ttu-id="4e753-122">Microsoft 커넥터에 대한 Veritas Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="4e753-123">이 계정을 만들하려면 [Veritas 고객 지원에 문의하세요.](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="4e753-123">To create this account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="4e753-124">1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="4e753-125">에서 사용자 지정 통합을 만들어 규정 준수 및 https://my.workplace.com/work/admin/apps/ eDiscovery 목적으로 API를 통해 Workplace에서 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-125">Create a custom integration at https://my.workplace.com/work/admin/apps/ to retrieve data from Workplace via APIs for compliance and eDiscovery purposes.</span></span>

   <span data-ttu-id="4e753-126">통합을 만들 때 Workplace 플랫폼은 인증에 사용되는 토큰을 생성하는 데 사용되는 고유한 자격 증명 집합을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-126">When creating the integration, the Workplace platform generates a set of unique credentials used to generate tokens that are used for authentication.</span></span> <span data-ttu-id="4e753-127">이러한 토큰은 2단계의 Facebook 커넥터 구성 마법사에서 Workplace에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-127">These tokens are used in the Workplace from Facebook connector configuration wizard in Step 2.</span></span> <span data-ttu-id="4e753-128">응용 프로그램을 만드는 방법에 대한 단계별 지침은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="4e753-128">For step-by step instructions about how to create the applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="4e753-129">1단계에서 Facebook 커넥터에서 Workplace를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-129">The user who creates the Workplace from Facebook connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="4e753-130">이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="4e753-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4e753-131">기본적으로 이 역할은 Exchange Online의 역할 그룹에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-131">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="4e753-132">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="4e753-133">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="4e753-134">자세한 내용은 "Exchange [](/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e753-134">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a><span data-ttu-id="4e753-135">1단계: Facebook 커넥터에서 Workplace 설정</span><span class="sxs-lookup"><span data-stu-id="4e753-135">Step 1: Set up the Workplace from Facebook connector</span></span>

<span data-ttu-id="4e753-136">첫 번째 단계는 Microsoft  365 규정 준수 센터의 데이터 커넥터 페이지에 액세스하고 Workplace 데이터에 대한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-136">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Workplace data.</span></span>

1. <span data-ttu-id="4e753-137">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 **Facebook에서 데이터** 커넥터  >  **Workplace를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e753-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Workplace from Facebook**.</span></span>

2. <span data-ttu-id="4e753-138">Facebook **제품 설명 페이지에서** 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e753-138">On the **Workplace from Facebook** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="4e753-139">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e753-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="4e753-140">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e753-140">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="4e753-141">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="4e753-142">2단계: Veritas Merge1 사이트에서 Facebook 커넥터에서 작업 공간 구성</span><span class="sxs-lookup"><span data-stu-id="4e753-142">Step 2: Configure the Workplace from Facebook connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="4e753-143">두 번째 단계는 Merge1 사이트에서 Facebook 커넥터에서 Workplace를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-143">The second step is to configure the Workplace from Facebook connector on the Merge1 site.</span></span> <span data-ttu-id="4e753-144">Facebook 커넥터에서 Workplace를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="4e753-144">For information about how to configure the Workplace from Facebook connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="4e753-145">저장 및 & **마친** 후  Microsoft 365 규정 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-145">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="4e753-146">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="4e753-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="4e753-147">사용자를 매핑하고 Microsoft 365 규정 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-147">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="4e753-148">외부 사용자를 **Microsoft 365** 사용자에 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-148">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="4e753-149">Workplace 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-149">The Workplace items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="4e753-150">커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 항목이 해당 사용자의 사서함으로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="4e753-151">**다음을** 클릭하고 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-151">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a><span data-ttu-id="4e753-152">4단계: Facebook 커넥터에서 작업 공간 모니터링</span><span class="sxs-lookup"><span data-stu-id="4e753-152">Step 4: Monitor the Workplace from Facebook connector</span></span>

<span data-ttu-id="4e753-153">Facebook 커넥터에서 Workplace를 만든 후 Microsoft 365 규정 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-153">After you create the Workplace from Facebook connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="4e753-154">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="4e753-155">커넥터 **탭을** 클릭한 다음 Facebook 커넥터에서 **Workplace를** 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-155">Click the **Connectors** tab and then select the **Workplace from Facebook** connector to display the flyout page.</span></span> <span data-ttu-id="4e753-156">이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-156">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="4e753-157">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-157">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="4e753-158">이 로그에는 Microsoft 클라우드로 가져온 데이터에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-158">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="4e753-159">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="4e753-159">Known issues</span></span>

- <span data-ttu-id="4e753-160">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="4e753-161">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e753-161">Support for larger items will be available at a later date.</span></span>