---
title: FX 파일 데이터를 커넥트 커넥터를 Microsoft 365
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
description: 관리자는 커넥터를 설정하여 Veritas FX 2013에서 데이터를 가져오고 보관할 커넥트 Microsoft 365. 이 커넥터를 사용하면 타사 데이터 원본의 데이터를 보관할 수 Microsoft 365 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 1efbe8d6d8cecdd8394b565abad4d33c8610398f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164264"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a><span data-ttu-id="6d5bf-104">FX 데이터 보관 커넥터 커넥트 설정</span><span class="sxs-lookup"><span data-stu-id="6d5bf-104">Set up a connector to archive FX Connect data</span></span>

<span data-ttu-id="6d5bf-105">Microsoft 365 준수 센터의 Veritas 커넥터를 사용하여 FX 커넥트 공동 작업 플랫폼에서 조직 내 사용자 사서함으로 데이터를 Microsoft 365 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the FX Connect collaboration platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="6d5bf-106">Veritas는 [FX](https://globanet.com/fx-connect/) 커넥트 항목을 캡처하고 해당 항목을 가져오도록 구성된 FX 커넥트 커넥터를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-106">Veritas provides an [FX Connect](https://globanet.com/fx-connect/) connector that is configured to capture FX Connect items and import those items to Microsoft 365.</span></span> <span data-ttu-id="6d5bf-107">커넥터는 거래, 메시지커넥트 기타 세부 정보 등 조직의 FX 커넥트 계정의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 조직의 사용자 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-107">The connector converts the content from FX Connect, such as  trades, messages, and other details from your organization's FX Connect account, to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="6d5bf-108">FX 커넥트 사서함에 저장한 후 소송 보존, eDiscovery Microsoft 365 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-108">After FX Connect data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="6d5bf-109">FX 커넥트 커넥터를 사용하여 조직의 데이터를 Microsoft 365 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-109">Using an FX Connect connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-fx-connect-data"></a><span data-ttu-id="6d5bf-110">보관 FX 데이터 커넥트 개요</span><span class="sxs-lookup"><span data-stu-id="6d5bf-110">Overview of archiving FX Connect data</span></span>

<span data-ttu-id="6d5bf-111">다음 개요에서는 커넥터를 사용하여 FX 서버의 FX 커넥트 보관하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-111">The following overview explains the process of using a connector to archive the FX Connect information in Microsoft 365.</span></span>

![FX 데이터 보관 커넥트 워크플로](../media/FXConnectConnectorWorkflow.png)

1. <span data-ttu-id="6d5bf-113">조직은 FX 서버와 함께 커넥트 FX 서버 커넥트 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-113">Your organization works with FX Connect to set up and configure an FX Connect site.</span></span>

2. <span data-ttu-id="6d5bf-114">24시간마다 한 번씩 FX 계정의 커넥트 Veritas Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-114">Once every 24 hours, items from FX Connect accounts are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="6d5bf-115">또한 커넥터는 FX 메시지 커넥트 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-115">The connector also converts the FX Connect items to an email message format.</span></span>

3. <span data-ttu-id="6d5bf-116">Microsoft 365 준수 센터에서 만드는 FX 커넥트 커넥터는 매일 Veritas Merge1 사이트에 연결하고 FX 커넥트 항목을 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-116">The FX Connect connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the FX Connect items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="6d5bf-117">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 특정 사용자의 사서함으로 항목을 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="6d5bf-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="6d5bf-118">FX 커넥트 폴더의 하위 폴더가 사용자 **사서함에** 만들어지며 해당 폴더로 항목이 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-118">A subfolder in the Inbox folder named **FX Connect** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="6d5bf-119">이 커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="6d5bf-120">모든 FX 커넥트 항목에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-120">Every FX Connect item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6d5bf-121">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6d5bf-121">Before you begin</span></span>

- <span data-ttu-id="6d5bf-122">Microsoft 커넥터에 대한 Veritas Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span>  <span data-ttu-id="6d5bf-123">계정을 만들하려면 [Veritas 고객 지원에 문의하세요.](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="6d5bf-123">To create an account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="6d5bf-124">1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="6d5bf-125">1단계에서 FX 커넥트 커넥터를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-125">The user who creates the FX Connect connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6d5bf-126">이 역할은 준수 센터의  데이터 커넥터 페이지에서 커넥터를 Microsoft 365 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6d5bf-127">기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="6d5bf-128">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6d5bf-129">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6d5bf-130">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-130">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-fx-connect-connector"></a><span data-ttu-id="6d5bf-131">1단계: FX 연결기 커넥트 설정</span><span class="sxs-lookup"><span data-stu-id="6d5bf-131">Step 1: Set up the FX Connect connector</span></span>

<span data-ttu-id="6d5bf-132">첫 번째 단계는 Microsoft 365  센터의 데이터 커넥터 페이지에 액세스하고 FX 커넥터 데이터용 커넥터를 커넥트 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for FX Connect data.</span></span>

1. <span data-ttu-id="6d5bf-133">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 **데이터** 커넥터  >  **FX** 커넥트.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **FX Connect**.</span></span>

2. <span data-ttu-id="6d5bf-134">**FX** 커넥트 설명 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d5bf-134">On the **FX Connect** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="6d5bf-135">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d5bf-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="6d5bf-136">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d5bf-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="6d5bf-137">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-fx-connect-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="6d5bf-138">2단계: Veritas Merge1 사이트에서 FX 커넥트 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="6d5bf-138">Step 2: Configure the FX Connect connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="6d5bf-139">두 번째 단계는 Merge1 사이트에서 FX 커넥트 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-139">The second step is to configure the FX Connect connector on the Merge1 site.</span></span> <span data-ttu-id="6d5bf-140">FX 커넥터를 구성하는 방법에 대한 자세한 커넥트 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="6d5bf-140">For information about how to configure the FX Connect connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="6d5bf-141">저장 및 & **마친** 후  준수 센터의 커넥터 마법사에 Microsoft 365 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="6d5bf-142">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="6d5bf-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="6d5bf-143">사용자를 매핑하고 Microsoft 365 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="6d5bf-144">FX **매핑 커넥트 사용자 Microsoft 365** 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-144">On the **Map FX Connect users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="6d5bf-145">FX 커넥트 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-145">The FX Connect items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="6d5bf-146">커넥터가 이 주소를 Microsoft 365 사용자 사서함으로 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="6d5bf-147">**다음을** 클릭하고 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-147">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-fx-connect-connector"></a><span data-ttu-id="6d5bf-148">4단계: FX 커넥터 커넥트 모니터링</span><span class="sxs-lookup"><span data-stu-id="6d5bf-148">Step 4: Monitor the FX Connect connector</span></span>

<span data-ttu-id="6d5bf-149">FX 커넥터를 만든 커넥트 준수 센터에서 커넥터 상태를 볼 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-149">After you create the FX Connect connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="6d5bf-150">으로 <https://compliance.microsoft.com/> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-150">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="6d5bf-151">커넥터 **탭을** 클릭한 다음 **FX** 커넥트 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-151">Click the **Connectors** tab and then select the **FX Connect** connector to display the flyout page.</span></span> <span data-ttu-id="6d5bf-152">이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="6d5bf-153">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="6d5bf-154">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6d5bf-155">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="6d5bf-155">Known issues</span></span>

- <span data-ttu-id="6d5bf-156">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="6d5bf-157">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5bf-157">Support for larger items will be available at a later date.</span></span>