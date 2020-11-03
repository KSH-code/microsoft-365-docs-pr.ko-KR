---
title: 교차 테넌트 사서함 마이그레이션
description: Microsoft 365 또는 Office 365 테 넌 트 간에 사서함을 이동 하는 방법입니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: a9f983cebfbed1482fca7e44b77c200cbd9574ac
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847121"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="05b3d-103">테 넌 트 사서함 마이그레이션 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="05b3d-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="05b3d-104">이전에는 Exchange Online 테 넌 트에서 사서함을 같은 Exchange Online 서비스의 다른 테 넌 트로 이동 해야 하는 경우 온-프레미스에 보드를 완전히 해제 한 다음 새 테 넌 트로 다시 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="05b3d-105">새 테 넌 트 사서함 마이그레이션 기능을 사용 하는 경우 원본 및 대상 테 넌 트에 포함 된 거주자 관리자는 온-프레미스 시스템에서 인프라 종속성이 최소화 된 테 넌 트 간에 사서함을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="05b3d-106">이렇게 하면 보드 및 온보드 사서함을 오프 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-106">This removes the need to offboard and onboard mailboxes.</span></span>

<span data-ttu-id="05b3d-107">일반적으로 합병 또는 divestitures 중에 사용자와 콘텐츠를 새 테 넌 트로 이동 하는 기능이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="05b3d-108">대상 테 넌 트 관리자가 이동을 실행 하면 온-프레미스에서 클라우드 온 보 딩 마이그레이션과 비슷한 끌어오기 이동 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="05b3d-109">테 넌 트 Exchange 사서함 이동은 테 넌 트 관리자가 완전히 셀프 서비스를 제공 하며, 사용자를 새 조직으로 전환 하는 데 필요한 더 큰 워크플로에 스크립팅할 수 있는 잘 알려진 인터페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="05b3d-110">관리자 `New-MigrationBatch` 는 사서함 이동 관리 역할을 통해 사용 가능한 cmdlet을 사용 하 여 테 넌 트 이동을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="05b3d-111">이동 프로세스에는 사서함 동기화 및 종료 중에 테 넌 트 권한 부여 검사가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="05b3d-112">마이그레이션 사용자가 테 넌 트 이동을 사용 하도록 설정 하려면 대상 테 넌 트 Exchange Online 시스템에서 MailUsers로 표시 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="05b3d-113">대상 테 넌 트에서 제대로 설정 되지 않은 사용자에 대 한 시스템 이동이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span> 

<span data-ttu-id="05b3d-114">이동이 완료 되 면 원본 시스템 사서함은 MailUser로 변환 되 고 Exchange에서 ExternalEmailAddress로 표시 된 targetAddress는 대상 테 넌 트에 대 한 라우팅 주소로 스탬프 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="05b3d-115">이 프로세스를 진행 하면 레거시 MailUser가 원본 테 넌 트에 남게 되 고 일정 기간 동안 및 메일 라우팅을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="05b3d-116">비즈니스 프로세스에서 허용 하는 경우 원본 테 넌 트에서 원본 메일 사용자를 제거 하거나이를 메일로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="05b3d-117">테 넌 트에 대 한 Exchange 사서함 마이그레이션은 하이브리드 또는 클라우드에서만 또는이 둘의 조합에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="05b3d-118">이 문서에서는 상호 테 넌 트 사서함 이동에 대 한 프로세스를 설명 하 고 콘텐츠 이동을 위해 원본 및 대상 테 넌 트를 준비 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span> 

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="05b3d-119">원본 및 대상 테 넌 트 준비</span><span class="sxs-lookup"><span data-stu-id="05b3d-119">Preparing source and target tenants</span></span>

<span data-ttu-id="05b3d-120">테 넌 트 Exchange 사서함 마이그레이션 기능을 사용 하려면 테 넌 트 마이그레이션에 대 한 권한 부여 및 범위 지정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="05b3d-121">이제 테 넌 트 관리자는 Azure Enterprise 응용 프로그램 및 키 자격 증명 모음 저장소 솔루션을 사용 하 여 테 넌 트 간에 Exchange Online 사서함 마이그레이션에 대 한 권한 부여 및 범위 지정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="05b3d-122">테 넌 트 사서함 이동은 초대 및 승인 모델을 지원 하 여 테 넌 트 쌍 간의 인증에 사용 되는 azure AD (azure Active Directory) 응용 프로그램을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="05b3d-123">조직 관계 및 마이그레이션 끝점과 같은 추가 구성 요소도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="05b3d-124">이 섹션에는 대상 디렉터리에서 MailUser 사용자 개체를 준비 하는 데 필요한 특정 단계는 포함 되지 않으며, 마이그레이션 일괄 처리를 전송 하는 예제 명령도 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="05b3d-125">이 정보는 [마이그레이션을 위한 대상 사용자 개체 준비를](#prepare-target-user-objects-for-migration) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05b3d-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05b3d-126">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="05b3d-126">Prerequisites</span></span>

<span data-ttu-id="05b3d-127">테 넌 트 사서함 이동 기능을 사용 하려면 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) 가 테 넌 트 쌍 별 azure 응용 프로그램을 설정 하 여 해당 테 넌 트에서 사서함 마이그레이션을 인증 하 고 권한을 부여 하는 데 사용할 인증서/비밀을 안전 하 게 저장 하 고 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="05b3d-128">시작 하기 전에 배포 스크립트를 실행 하 여 Azure 키 자격 증명, 이동 사서함 응용 프로그램, EXO 마이그레이션 끝점 및 EXO 조직 관계를 구성 하기 위해 필요한 권한이 있는지를 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="05b3d-129">일반적으로 전역 관리자에 게는 모든 구성 단계를 수행할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="05b3d-130">또한 설치 프로그램을 실행 하기 전에 원본 테 넌 트에서 메일 사용이 가능한 보안 그룹이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="05b3d-131">이러한 그룹은 원본 (또는 리소스 라고도 함) 테 넌 트에서 대상 테 넌 트로 이동할 수 있는 사서함 목록의 범위를 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="05b3d-132">따라서 원본 테 넌 트 관리자는 이동 해야 하는 특정 사서함 집합을 제한 하거나 범위를 지정할 수 있으므로 의도 하지 않은 사용자를 마이그레이션하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="05b3d-133">중첩 그룹은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-133">Nested groups are not supported.</span></span>

<span data-ttu-id="05b3d-134">또한 사서함을 이동할 수 있는 신뢰할 수 있는 파트너 회사와 통신 하 여 해당 Microsoft 365 테 넌 트 ID를 얻도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="05b3d-135">이 테 넌 트 ID는 조직 관계 필드에서 사용 됩니다 `DomainName` .</span><span class="sxs-lookup"><span data-stu-id="05b3d-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="05b3d-136">구독의 테 넌 트 ID를 가져오려면 Microsoft 365 관리 센터에 로그인 하 고로 이동 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="05b3d-137">테 넌 트 ID 속성에 대 한 복사 아이콘을 클릭 하 여 클립보드에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="05b3d-138">프로세스의 작동 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="사서함 마이그레이션에 대 한 테 넌 트 준비":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="05b3d-140">테 넌 트 준비</span><span class="sxs-lookup"><span data-stu-id="05b3d-140">Prepare tenants</span></span>

<span data-ttu-id="05b3d-141">높은 수준에서는 설치 스크립트를 실행할 때 다음과 같은 구성 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-141">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="05b3d-142">대상 테 넌 트 준비:</span><span class="sxs-lookup"><span data-stu-id="05b3d-142">Prepare the target tenant:</span></span>

1. <span data-ttu-id="05b3d-143">기존 Azure 리소스 그룹을 제공 하지 않으면 새 항목을 만듭니다 (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="05b3d-143">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="05b3d-144">기존 키 보관소를 제공 하지 않으면 새로 생성 됩니다 (스크립트).</span><span class="sxs-lookup"><span data-stu-id="05b3d-144">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="05b3d-145">Office 365 Exchange Online 사서함 마이그레이션 응용 프로그램 (스크립트)에 대 한 새 액세스 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-145">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="05b3d-146">새 인증서를 만들거나 (지정 된 경우) 마이그레이션 응용 프로그램 (스크립트)에 대 한 비밀을 보존 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-146">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="05b3d-147">새 Azure AD 응용 프로그램을 만듭니다 (스크립트).</span><span class="sxs-lookup"><span data-stu-id="05b3d-147">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="05b3d-148">인증서/암호가 마이그레이션 응용 프로그램 (스크립트)에 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-148">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="05b3d-149">사서함 마이그레이션 사용 권한은 응용 프로그램 (스크립트)에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-149">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="05b3d-150">배포 스크립트는 대상 관리자가 자체 응용 프로그램 (스크립트)을 consents 때까지 일시 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-150">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="05b3d-151">대상 테 넌 트 관리자가 응용 프로그램에 부여 된 사용 권한 (수동)을 consents 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-151">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="05b3d-152">대상 테 넌 트 (스크립트)에 대 한 조직 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-152">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="05b3d-153">대상 테 넌 트 (스크립트)로 사서함을 가져오기 위한 마이그레이션 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-153">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="05b3d-154">원본 테 넌 트 준비:</span><span class="sxs-lookup"><span data-stu-id="05b3d-154">Prepare the source tenant:</span></span>

1. <span data-ttu-id="05b3d-155">원본 테 넌 트 관리자는 대상 테 넌 트 (수동)에서 사서함 마이그레이션 응용 프로그램 초대에 대 한 동의를 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-155">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="05b3d-156">원본 테 넌 트 관리자는 마이그레이션 응용 프로그램 (수동)에 의해 이동 될 수 있는 사서함 목록을 포함 하기 위해 테 넌 트에 메일 사용이 가능한 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-156">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="05b3d-157">조직 관계는 OAuth 확인에 사서함 마이그레이션 응용 프로그램을 사용 하 여 이동 요청 (스크립트)을 수락 하도록 지정 하는 대상 테 넌 트에 대해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-157">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="05b3d-158">대상 테 넌 트 관리에 대 한 단계별 지침</span><span class="sxs-lookup"><span data-stu-id="05b3d-158">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="05b3d-159">[GitHub 리포지토리에서](https://github.com/microsoft/cross-tenant/releases/tag/Preview)대상 테 넌 트 설정에 대 한 SetupCrossTenantRelationshipForTargetTenant.ps1 스크립트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-159">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="05b3d-160">스크립트를 실행할 컴퓨터에 스크립트 (SetupCrossTenantRelationshipForTargetTenant.ps1)를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-160">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="05b3d-161">Exchange Online 대상 테 넌 트에 대 한 원격 PowerShell 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-161">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="05b3d-162">Azure 키 자격 증명 저장소 및 인증서, 이동 사서함 응용 프로그램, EXO 마이그레이션 끝점 및 EXO 조직 관계를 구성 하기 위해 배포 스크립트를 실행 하는 데 필요한 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-162">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="05b3d-163">파일 폴더 디렉터리를 스크립트 위치로 변경 하거나 스크립트가 현재 원격 PowerShell 세션의 현재 위치에 저장 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-163">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="05b3d-164">다음 매개 변수와 값을 사용 하 여 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-164">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="05b3d-165">매개 변수</span><span class="sxs-lookup"><span data-stu-id="05b3d-165">Parameter</span></span> | <span data-ttu-id="05b3d-166">값</span><span class="sxs-lookup"><span data-stu-id="05b3d-166">Value</span></span> | <span data-ttu-id="05b3d-167">필수 또는 선택 사항</span><span class="sxs-lookup"><span data-stu-id="05b3d-167">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="05b3d-168">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="05b3d-168">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="05b3d-169">원본 테 넌 트 도메인 (예: fabrikam \. onmicrosoft.com)</span><span class="sxs-lookup"><span data-stu-id="05b3d-169">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="05b3d-170">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-170">Required</span></span> |
    | <span data-ttu-id="05b3d-171">-Resourceten앤틸리스 전자 메일</span><span class="sxs-lookup"><span data-stu-id="05b3d-171">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="05b3d-172">원본 테 넌 트 관리자의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-172">Source tenant admin’s email address.</span></span> <span data-ttu-id="05b3d-173">대상 관리자가 보낸 사서함 마이그레이션 응용 프로그램을 사용 하기 위해 consenting 되는 원본 테 넌 트 관리자입니다. 응용 프로그램에 대 한 전자 메일 초대를 받을 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-173">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="05b3d-174">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-174">Required</span></span> |
    | <span data-ttu-id="05b3d-175">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="05b3d-175">-TargetTenantDomain</span></span>                         | <span data-ttu-id="05b3d-176">대상 테 넌 트 도메인 (예: contoso \. onmicrosoft.com)</span><span class="sxs-lookup"><span data-stu-id="05b3d-176">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="05b3d-177">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-177">Required</span></span> |
    | <span data-ttu-id="05b3d-178">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="05b3d-178">-ResourceTenantId</span></span>                           | <span data-ttu-id="05b3d-179">원본 테 넌 트 조직 ID (GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-179">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="05b3d-180">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-180">Required</span></span> |
    | <span data-ttu-id="05b3d-181">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="05b3d-181">-SubscriptionId</span></span>                             | <span data-ttu-id="05b3d-182">리소스를 만드는 데 사용할 Azure 구독입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-182">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="05b3d-183">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-183">Required</span></span> |
    | <span data-ttu-id="05b3d-184">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="05b3d-184">-ResourceGroup</span></span>                              | <span data-ttu-id="05b3d-185">키 자격 증명 모음을 포함 하거나 포함 하는 Azure 리소스 그룹 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-185">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="05b3d-186">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-186">Required</span></span> |
    | <span data-ttu-id="05b3d-187">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="05b3d-187">-KeyVaultName</span></span>                               | <span data-ttu-id="05b3d-188">사서함 마이그레이션 응용 프로그램 인증서/비밀을 저장할 Azure 키 자격 증명 모음 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-188">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="05b3d-189">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-189">Required</span></span> |
    | <span data-ttu-id="05b3d-190">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="05b3d-190">-CertificateName</span></span>                            | <span data-ttu-id="05b3d-191">키 자격 증명 모음에서 인증서를 생성 하거나 검색할 때의 인증서 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-191">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="05b3d-192">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-192">Required</span></span> |
    | <span data-ttu-id="05b3d-193">-CertificateSubject 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-193">-CertificateSubject</span></span>                         | <span data-ttu-id="05b3d-194">Azure 키 자격 증명 모음 인증서 주체 이름 (예: CN = contoso_fabrikam)입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-194">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="05b3d-195">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-195">Required</span></span> |
    | <span data-ttu-id="05b3d-196">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="05b3d-196">-ExistingApplicationId</span></span>                      | <span data-ttu-id="05b3d-197">메일 마이그레이션 응용 프로그램이 이미 만들어진 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-197">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="05b3d-198">선택</span><span class="sxs-lookup"><span data-stu-id="05b3d-198">Optional</span></span> |
    | <span data-ttu-id="05b3d-199">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="05b3d-199">-AzureAppPermissions</span></span>                        | <span data-ttu-id="05b3d-200">사서함 마이그레이션 응용 프로그램에 부여 해야 하는 사용 권한 (예: Exchange 또는 MSGraph) (이 응용 프로그램을 사용 하 여 리소스 테 넌 트에 대 한 승인 연결 초대를 전송 하는 데 필요한 MSGraph, 사서함 이동에 대 한 Exchange)</span><span class="sxs-lookup"><span data-stu-id="05b3d-200">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="05b3d-201">필수</span><span class="sxs-lookup"><span data-stu-id="05b3d-201">Required</span></span> |
    | <span data-ttu-id="05b3d-202">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="05b3d-202">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="05b3d-203">마이그레이션에 대해 만든 응용 프로그램을 사용 하 여 승인 링크 초대를 원본 테 넌 트 관리자에 게 보내는 데 사용 하는 매개 변수입니다. 이 매개 변수가 없으면 대상 관리자의 자격 증명을 입력 하 라는 메시지가 Azure 초대 관리자에 연결 하 고 대상 관리자로 초대를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-203">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="05b3d-204">선택</span><span class="sxs-lookup"><span data-stu-id="05b3d-204">Optional</span></span> |
    | <span data-ttu-id="05b3d-205">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="05b3d-205">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="05b3d-206">키 자격 증명 모음의 감사 로그가 저장 되는 저장소 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-206">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="05b3d-207">선택</span><span class="sxs-lookup"><span data-stu-id="05b3d-207">Optional</span></span> |
    | <span data-ttu-id="05b3d-208">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="05b3d-208">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="05b3d-209">키 자격 증명 모음 감사 로그를 저장 하기 위한 저장소 계정이 포함 된 리소스 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-209">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="05b3d-210">선택</span><span class="sxs-lookup"><span data-stu-id="05b3d-210">Optional</span></span> |
    ||||

6. <span data-ttu-id="05b3d-211">스크립트를 일시 중지 하 고이 프로세스 중에 만들어진 Exchange 사서함 마이그레이션 응용 프로그램에 대 한 수락 또는 동의를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-211">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="05b3d-212">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-212">Here is an example.</span></span>

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ``` 

7. <span data-ttu-id="05b3d-213">원격 PowerShell 세션에 URL이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-213">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="05b3d-214">테 넌 트 동의를 위해 제공 된 링크를 복사한 다음 웹 브라우저에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-214">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="05b3d-215">전역 관리자 자격 증명으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-215">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="05b3d-216">다음 화면이 표시 되 면 **수락** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-216">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="사용 권한 수락 대화 상자":::
    
9. <span data-ttu-id="05b3d-218">원격 PowerShell 세션으로 다시 전환한 다음 Enter 키를 눌러 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-218">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="05b3d-219">이 스크립트는 나머지 설치 개체를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-219">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="05b3d-220">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-220">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="05b3d-221">이제 대상 관리자 설치가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-221">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="05b3d-222">원본 테 넌 트 관리자를 위한 단계별 지침</span><span class="sxs-lookup"><span data-stu-id="05b3d-222">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="05b3d-223">설정 하는 동안 대상 관리자가 지정한-Resourceten앤틸리스 전자 메일로 사서함에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-223">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="05b3d-224">대상 테 넌 트에서 전자 메일 초대를 찾은 다음 **시작** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-224">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="초대 받은 대화 상자":::

2. <span data-ttu-id="05b3d-226">**수락** 을 선택 하 여 초대를 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-226">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="사용 권한을 허용 하는 대화 상자":::

   > [!NOTE]
   > <span data-ttu-id="05b3d-228">이 전자 메일을 받지 않거나 찾을 수 없는 경우 대상 테 넌 트 관리자에 게는 초대를 수락 하도록 사용자에 게 제공할 수 있는 직접 URL이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-228">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="05b3d-229">URL은 대상 테 넌 트 관리자의 원격 PowerShell 세션에 대 한 성적의 기록에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-229">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="05b3d-230">Microsoft 365 관리 센터 또는 원격 PowerShell 세션에서 하나 이상의 메일 사용이 가능한 보안 그룹을 만들어 대상 테 넌 트에서 대상 테 넌 트로 끌어오기 (이동) 할 사서함 목록을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-230">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="05b3d-231">이 그룹을 미리 채우지 않아도 되지만 설치 단계 (스크립트)를 실행 하려면 하나 이상의 그룹을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-231">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="05b3d-232">그룹 중첩은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-232">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="05b3d-233">[여기](https://github.com/microsoft/cross-tenant/releases/tag/Preview)에서 GitHub 리포지토리에서 원본 테 넌 트 설정에 대 한 SetupCrossTenantRelationshipForTargetResource.ps1 스크립트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-233">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository [here](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="05b3d-234">Exchange 관리자 권한을 사용 하 여 원본 테 넌 트에 대 한 원격 PowerShell 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-234">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="05b3d-235">전역 관리자 권한은 원본 테 넌 트를 구성 하는 데 필요 하지 않으며, Azure 응용 프로그램 만들기 프로세스 때문에 대상 테 넌 트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-235">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="05b3d-236">스크립트 위치로 디렉터리를 변경 하거나 스크립트가 현재 원격 PowerShell 세션의 현재 위치에 저장 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-236">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="05b3d-237">다음 필수 매개 변수 및 값을 사용 하 여 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-237">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="05b3d-238">매개 변수</span><span class="sxs-lookup"><span data-stu-id="05b3d-238">Parameter</span></span> | <span data-ttu-id="05b3d-239">값</span><span class="sxs-lookup"><span data-stu-id="05b3d-239">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="05b3d-240">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="05b3d-240">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="05b3d-241">마이그레이션 범위에 있는 id/사서함에 대해 원본 테 넌 트에서 만든 메일 사용이 가능한 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-241">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="05b3d-242">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="05b3d-242">-ResourceTenantDomain</span></span> | <span data-ttu-id="05b3d-243">원본 테 넌 트 도메인 이름 (예: fabrikam \. onmicrosoft.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-243">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="05b3d-244">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="05b3d-244">-TargetTenantDomain</span></span> | <span data-ttu-id="05b3d-245">대상 테 넌 트 도메인 이름 (예: contoso \. onmicrosoft.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-245">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="05b3d-246">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="05b3d-246">-ApplicationId</span></span> | <span data-ttu-id="05b3d-247">마이그레이션에 사용 되는 응용 프로그램의 Azure 응용 프로그램 ID (GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-247">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="05b3d-248">Azure portal (Azure AD, Enterprise 응용 프로그램, 앱 이름, 응용 프로그램 ID)을 통해 사용할 수 있는 응용 프로그램 ID 또는 초대 전자 메일에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-248">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="05b3d-249">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="05b3d-249">-TargetTenantId</span></span> | <span data-ttu-id="05b3d-250">대상 테 넌 트의 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-250">Tenant ID of the target tenant.</span></span> <span data-ttu-id="05b3d-251">예를 들어 contoso \. onmicrosoft.com 테 넌 트의 AZURE AD 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-251">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||
    
    <span data-ttu-id="05b3d-252">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-252">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="05b3d-253">이제 원본 관리자 설치가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-253">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="05b3d-254">설치 확인</span><span class="sxs-lookup"><span data-stu-id="05b3d-254">Verify setup</span></span>

<span data-ttu-id="05b3d-255">원본 및 대상 테 넌 트 및 대상에 있는 마이그레이션 끝점 모두의 조직 관계가 성공적으로 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-255">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="05b3d-256">대상 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="05b3d-256">Target tenant</span></span>

<span data-ttu-id="05b3d-257">**조직 관계**</span><span class="sxs-lookup"><span data-stu-id="05b3d-257">**Organization relationship**</span></span>

<span data-ttu-id="05b3d-258">이 명령을 사용 하 여 조직 관계 개체를 만들고 구성 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-258">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="05b3d-259">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-259">Here is an example:</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="05b3d-260">**마이그레이션 끝점**</span><span class="sxs-lookup"><span data-stu-id="05b3d-260">**Migration endpoint**</span></span>

<span data-ttu-id="05b3d-261">이 명령을 사용 하 여 마이그레이션 끝점 개체를 만들고 구성 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-261">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="05b3d-262">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-262">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="05b3d-263">원본 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="05b3d-263">Source tenant</span></span>

<span data-ttu-id="05b3d-264">**조직 관계**</span><span class="sxs-lookup"><span data-stu-id="05b3d-264">**Organization relationship**</span></span>

<span data-ttu-id="05b3d-265">이 명령을 사용 하 여 조직 관계 개체를 만들고 구성 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-265">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
<span data-ttu-id="05b3d-266">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-266">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="05b3d-267">원본으로 사서함 다시 이동</span><span class="sxs-lookup"><span data-stu-id="05b3d-267">Move mailboxes back to the original source</span></span>

<span data-ttu-id="05b3d-268">사서함이 원래 원본 테 넌 트로 다시 이동 해야 하는 경우 동일한 단계 및 스크립트 집합을 새 원본과 새 대상 테 넌 트 둘 다에서 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-268">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="05b3d-269">기존 조직 관계 개체가 다시 만들어지지 않고 업데이트 되거나 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-269">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="05b3d-270">마이그레이션을 위한 대상 사용자 개체 준비</span><span class="sxs-lookup"><span data-stu-id="05b3d-270">Prepare target user objects for migration</span></span>

<span data-ttu-id="05b3d-271">사용자를 마이그레이션하는 작업은 대상 테 넌 트 및 Exchange Online 시스템 (MailUsers)에 특정 특성을 표시 하 여 테 넌 트 이동이 가능 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-271">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="05b3d-272">대상 테 넌 트에서 제대로 설정 되지 않은 사용자에 대 한 시스템 이동이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-272">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="05b3d-273">다음 섹션에서는 대상 테 넌 트에 대 한 MailUser 개체 요구 사항을 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-273">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="05b3d-274">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="05b3d-274">Prerequisites</span></span>
  
<span data-ttu-id="05b3d-275">다음 개체 및 특성이 대상 조직에 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-275">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="05b3d-276">원본 조직에서 이동 하는 사서함의 경우 대상 조직에서 MailUser 개체를 프로 비전 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-276">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 
   - <span data-ttu-id="05b3d-277">대상 MailUser는 원본 사서함에서 다음 특성을 갖고 있거나 새 사용자 개체를 사용 하 여 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-277">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="05b3d-278">ExchangeGUID (원본에서 대상으로 직접 흐름)-사서함 GUID가 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-278">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="05b3d-279">대상 개체에 없는 경우에는 이동 프로세스가 진행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-279">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="05b3d-280">ArchiveGUID (원본에서 대상으로 직접 흐름)-보관 GUID가 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-280">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="05b3d-281">대상 개체에 없는 경우에는 이동 프로세스가 진행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-281">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="05b3d-282">(원본 사서함이 사용 하도록 설정 된 경우에만 필요).</span><span class="sxs-lookup"><span data-stu-id="05b3d-282">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="05b3d-283">LegacyExchangeDN (proxyAddress, "x500: <LegacyExchangeDN> ")-legacyexchangedn은 대상 MailUser에 x500: proxyAddress로 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-283">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="05b3d-284">대상 개체에 없는 경우에는 이동 프로세스가 진행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-284">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="05b3d-285">UserPrincipalName – UPN은 사용자의 새 id 또는 대상 회사 (예: user@northwindtraders.onmicrosoft.com)에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-285">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="05b3d-286">Primary SMTPAddress-기본 SMTP 주소가 사용자의 새 회사 (예: user@northwind.com)에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-286">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="05b3d-287">TargetAddress/ExternalEmailAddress – MailUser는 원본 테 넌 트에 호스트 된 사용자의 현재 사서함을 참조 합니다 (예: user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="05b3d-287">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="05b3d-288">이 값을 할당할 때 PrimarySMTPAddress도 할당 하거나이 값에 의해 이동 오류가 발생할 PrimarySMTPAddress이 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-288">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="05b3d-289">원본 사서함의 레거시 smtp 프록시 주소를 대상 MailUser에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-289">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="05b3d-290">예를 들어 fabrikam.onmicrosoft.com 테 넌 트 개체에서 MEU의 contoso.com를 유지 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-290">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="05b3d-291">도메인은 하나의 Azure AD 또는 Exchange Online 테 넌 트에만 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-291">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
    <span data-ttu-id="05b3d-292">예제 **대상** mailuser 개체:</span><span class="sxs-lookup"><span data-stu-id="05b3d-292">Example **target** MailUser object:</span></span>
 
    | <span data-ttu-id="05b3d-293">특성</span><span class="sxs-lookup"><span data-stu-id="05b3d-293">Attribute</span></span>             | <span data-ttu-id="05b3d-294">값</span><span class="sxs-lookup"><span data-stu-id="05b3d-294">Value</span></span>                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="05b3d-295">별칭</span><span class="sxs-lookup"><span data-stu-id="05b3d-295">Alias</span></span>                 | <span data-ttu-id="05b3d-296">LaraN</span><span class="sxs-lookup"><span data-stu-id="05b3d-296">LaraN</span></span>                                                                                                                    |
    | <span data-ttu-id="05b3d-297">RecipientType</span><span class="sxs-lookup"><span data-stu-id="05b3d-297">RecipientType</span></span>         | <span data-ttu-id="05b3d-298">Enable-mailuser</span><span class="sxs-lookup"><span data-stu-id="05b3d-298">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="05b3d-299">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="05b3d-299">RecipientTypeDetails</span></span>  | <span data-ttu-id="05b3d-300">Enable-mailuser</span><span class="sxs-lookup"><span data-stu-id="05b3d-300">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="05b3d-301">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="05b3d-301">UserPrincipalName</span></span>     | <span data-ttu-id="05b3d-302">LaraN@northwintraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="05b3d-302">LaraN@northwintraders\.onmicrosoft.com</span></span>                                                                                    |
    | <span data-ttu-id="05b3d-303">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="05b3d-303">PrimarySmtpAddress</span></span>    | <span data-ttu-id="05b3d-304">Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="05b3d-304">Lara\.Newton@northwind.com</span></span>                                                                                                |
    | <span data-ttu-id="05b3d-305">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="05b3d-305">ExternalEmailAddress</span></span>  | <span data-ttu-id="05b3d-306">SMTP: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="05b3d-306">SMTP:LaraN@contoso\.onmicrosoft.com</span></span>                                                                                       |
    | <span data-ttu-id="05b3d-307">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="05b3d-307">ExchangeGuid</span></span>          | <span data-ttu-id="05b3d-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="05b3d-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
    | <span data-ttu-id="05b3d-309">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="05b3d-309">LegacyExchangeDN</span></span>      | <span data-ttu-id="05b3d-310">/o = 첫 번째 조직/ou = Exchange 관리 그룹</span><span class="sxs-lookup"><span data-stu-id="05b3d-310">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
    |                       | <span data-ttu-id="05b3d-311">(FYDIBOHF23SPDLT)/recn = Recipients/cn = 74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="05b3d-311">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
    | <span data-ttu-id="05b3d-312">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="05b3d-312">EmailAddresses</span></span>        | <span data-ttu-id="05b3d-313">x500:/o = 첫 번째 조직/ou = Exchange 관리 그룹 (FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="05b3d-313">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
    |                       | <span data-ttu-id="05b3d-314">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="05b3d-314">7273f1f9-Lara</span></span>                                                                                                            |
    |                       | <span data-ttu-id="05b3d-315">smtp: LaraN@northwindtraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="05b3d-315">smtp:LaraN@northwindtraders\.onmicrosoft.com</span></span>                                                                              |
    |                       | <span data-ttu-id="05b3d-316">SMTP: Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="05b3d-316">SMTP:Lara\.Newton@northwind.com</span></span>                                                                                           |
    |||

   <span data-ttu-id="05b3d-317">예제 **원본** 사서함 개체:</span><span class="sxs-lookup"><span data-stu-id="05b3d-317">Example **source** Mailbox object:</span></span>

   | <span data-ttu-id="05b3d-318">특성</span><span class="sxs-lookup"><span data-stu-id="05b3d-318">Attribute</span></span>             | <span data-ttu-id="05b3d-319">값</span><span class="sxs-lookup"><span data-stu-id="05b3d-319">Value</span></span>                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | <span data-ttu-id="05b3d-320">별칭</span><span class="sxs-lookup"><span data-stu-id="05b3d-320">Alias</span></span>                 | <span data-ttu-id="05b3d-321">LaraN</span><span class="sxs-lookup"><span data-stu-id="05b3d-321">LaraN</span></span>                                                                    |
   | <span data-ttu-id="05b3d-322">RecipientType</span><span class="sxs-lookup"><span data-stu-id="05b3d-322">RecipientType</span></span>         | <span data-ttu-id="05b3d-323">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="05b3d-323">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="05b3d-324">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="05b3d-324">RecipientTypeDetails</span></span>  | <span data-ttu-id="05b3d-325">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="05b3d-325">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="05b3d-326">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="05b3d-326">UserPrincipalName</span></span>     | <span data-ttu-id="05b3d-327">LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="05b3d-327">LaraN@contoso\.onmicrosoft.com</span></span>                                            |
   | <span data-ttu-id="05b3d-328">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="05b3d-328">PrimarySmtpAddress</span></span>    | <span data-ttu-id="05b3d-329">Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="05b3d-329">Lara\.Newton@contoso.com</span></span>                                                  |
   | <span data-ttu-id="05b3d-330">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="05b3d-330">ExchangeGuid</span></span>          | <span data-ttu-id="05b3d-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="05b3d-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
   | <span data-ttu-id="05b3d-332">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="05b3d-332">LegacyExchangeDN</span></span>      | <span data-ttu-id="05b3d-333">/o = 첫 번째 조직/ou = Exchange 관리 그룹</span><span class="sxs-lookup"><span data-stu-id="05b3d-333">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
   |                       | <span data-ttu-id="05b3d-334">(FYDIBOHF23SPDLT)/recn = Recipients/cn = d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="05b3d-334">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
   | <span data-ttu-id="05b3d-335">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="05b3d-335">EmailAddresses</span></span>        | <span data-ttu-id="05b3d-336">smtp: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="05b3d-336">smtp:LaraN@contoso\.onmicrosoft.com</span></span> 
   |                       | <span data-ttu-id="05b3d-337">SMTP: Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="05b3d-337">SMTP:Lara\.Newton@contoso.com</span></span>          |
   |||

   - <span data-ttu-id="05b3d-338">추가 특성은 Exchange 하이브리드 쓰기에 이미 포함 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-338">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="05b3d-339">그렇지 않으면 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-339">If not, they should be included.</span></span> 
   - <span data-ttu-id="05b3d-340">msExchBlockedSendersHash – 클라이언트의 온라인 수신 허용 및 수신 거부 데이터를 온-프레미스 Active Directory에 다시 씁니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-340">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="05b3d-341">msExchSafeRecipientsHash – 클라이언트의 온라인 수신 허용 및 수신 거부 데이터를 온-프레미스 Active Directory에 다시 씁니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-341">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="05b3d-342">msExchSafeSendersHash – 클라이언트의 온라인 수신 허용 및 수신 거부 데이터를 온-프레미스 Active Directory에 다시 씁니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-342">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="05b3d-343">원본 사서함이 LitigationHold에 있고 원본 사서함 복구 가능한 항목 크기가 데이터베이스 기본값 (30gb) 보다 크면 대상 할당량이 원본 사서함 크기 보다 작기 때문에 이동을 진행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-343">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="05b3d-344">대상 MailUser 개체를 업데이트 하 여 ELC 사서함 플래그를 원본 환경에서 대상으로 전환 하 여 대상 시스템이 MailUser의 할당량을 100 g b로 확장 하 여 대상으로 이동할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-344">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="05b3d-345">이 지침은 ELC 플래그 스탬프 명령을 사용 하 여 테 넌 트 관리자에 게 노출 되지 않으므로 Azure AD Connect를 실행 하는 하이브리드 id에 대해서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-345">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="05b3d-346">샘플-보증 없음</span><span class="sxs-lookup"><span data-stu-id="05b3d-346">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="05b3d-347">이 스크립트는 원본 사서함 (원본 값 가져오기)과 대상 온-프레미스 Active Directory (ADUser 개체 스탬프 지정)에 대 한 연결을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-347">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="05b3d-348">원본에 소송 또는 단일 항목 복구가 사용 하도록 설정 되어 있는 경우 대상 계정에서이를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-348">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="05b3d-349">이렇게 하면 대상 계정의 휴지통 크기가 100 GB로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-349">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. <span data-ttu-id="05b3d-350">비 하이브리드 대상 테 넌 트는 Mailusers 개체에 대 한 소송 보존을 사용 하도록 설정 하 고 할당량을 100 GB로 늘리기 위해 다음 명령을 실행 하 여, 마이그레이션 전에 MailUsers에 대 한 복구 가능한 항목 폴더의 할당량을 수정할 수 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-350">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="05b3d-351">참고 하이브리드의 테 넌 트에 대해서는이 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-351">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="05b3d-352">대상 조직의 사용자에 게는 조직에 적합 한 Exchange Online 구독을 사용할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-352">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="05b3d-353">사서함 이동이 진행 되는 동안에는 라이선스를 적용할 수 있지만 대상 MailUser가 ExchangeGUID 및 프록시 주소로 제대로 설정 된 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-353">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="05b3d-354">ExchangeGUID을 적용 하기 전에 라이선스를 적용 하면 대상 조직에 새 사서함이 프로 비전 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-354">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="05b3d-355">사서함 또는 MailUser 개체에 라이선스를 적용 하는 경우 모든 SMTP 유형 proxyAddresses가 scrubbed 되어 확인 된 도메인만 Exchange EmailAddresses 배열에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-355">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="05b3d-356">대상 MailUser에 원본 ExchangeGuid와 일치 하지 않는 이전 ExchangeGuid가 없는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-356">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="05b3d-357">이 문제는 대상 MEU가 이전에 Exchange Online에 대해 사용이 허가 되었으며 사서함이 프로 비전 된 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-357">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="05b3d-358">대상 MailUser가 이전에 사용이 허가 되었거나 원본 ExchangeGuid와 일치 하지 않는 ExchangeGuid 있는 경우 클라우드 MEU 정리를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-358">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="05b3d-359">이러한 클라우드 MEUs의 경우 명령을 실행할 수 있습니다 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .</span><span class="sxs-lookup"><span data-stu-id="05b3d-359">For these cloud MEUs, you can run the `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` command.</span></span> 

    > [!Caution]
    > <span data-ttu-id="05b3d-360">이 프로세스는 되돌릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-360">This process is irreversible.</span></span> <span data-ttu-id="05b3d-361">개체에 소프트 삭제 된 사서함이 있는 경우이 지점 이후에는 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-361">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="05b3d-362">하지만 올바른 ExchangeGuid를 대상 개체에 동기화 할 수는 있지만 MRS에서는 원본 사서함을 새로 만든 대상 사서함에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-362">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="05b3d-363">새 매개 변수에서 EHLO 블로그를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-363">(Reference EHLO blog on the new parameter.)</span></span> 
 
    <span data-ttu-id="05b3d-364">이 명령을 사용 하 여 이전에 사서함 이었던 개체를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-364">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    <span data-ttu-id="05b3d-365">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-365">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    <span data-ttu-id="05b3d-366">이 명령을 사용 하 여 일시 삭제 된 사서함의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-366">Clear the soft-deleted mailbox using this command.</span></span>

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    <span data-ttu-id="05b3d-367">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-367">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="05b3d-368">사서함 마이그레이션 수행</span><span class="sxs-lookup"><span data-stu-id="05b3d-368">Perform mailbox migrations</span></span>

<span data-ttu-id="05b3d-369">테 넌 트 Exchange 사서함 마이그레이션은 대상 테 넌 트에서 시작 되는 마이그레이션 일괄 처리로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-369">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="05b3d-370">이는 Exchange 온-프레미스에서 Microsoft 365으로 마이그레이션할 때 탑재 된 마이그레이션 일괄 처리가 작동 하는 방식과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-370">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="05b3d-371">마이그레이션 일괄 처리 만들기</span><span class="sxs-lookup"><span data-stu-id="05b3d-371">Create Migration batches</span></span>

<span data-ttu-id="05b3d-372">다음은 kicking 끄기 이동에 대 한 예제 마이그레이션 일괄 처리 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-372">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="05b3d-373">CSV 파일의 전자 메일 주소는 원본 테 넌 트가 아닌 대상 테 넌 트에 지정 된 것 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-373">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="05b3d-374">또한 마이그레이션 일괄 처리는 테 넌 트 옵션을 선택할 때 새 Exchange 관리 센터에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-374">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>
 
#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="05b3d-375">온-프레미스 MailUsers 업데이트</span><span class="sxs-lookup"><span data-stu-id="05b3d-375">Update on-premises MailUsers</span></span>

<span data-ttu-id="05b3d-376">사서함이 원본에서 대상으로 이동한 후에는 원본 및 대상 모두의 온-프레미스 메일 사용자가 새 targetAddress 업데이트 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-376">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="05b3d-377">예제에서 이동에 사용 되는 targetDeliveryDomain는 **contoso \. onmicrosoft.com** 입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-377">In the examples, the targetDeliveryDomain used in the move is **contoso\.onmicrosoft.com**.</span></span> <span data-ttu-id="05b3d-378">이 targetAddress를 사용 하 여 메일 사용자를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-378">Update the mail users with this targetAddress.</span></span>
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="05b3d-379">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="05b3d-379">Frequently asked questions</span></span>
 
<span data-ttu-id="05b3d-380">**이동 후 원본 온-프레미스에서 RemoteMailboxes을 업데이트 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="05b3d-380">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>
 
<span data-ttu-id="05b3d-381">예, 원본 테 넌 트 사서함이 대상 테 넌 트로 이동 하는 경우 원본 온-프레미스 사용자의 targetAddress (RemoteRoutingAddress/ExternalEmailAddress)를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-381">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="05b3d-382">메일 라우팅은 서로 다른 targetAddresses를 사용 하는 여러 메일 사용자 간의 참조를 따를 수 있지만 메일 사용자에 대 한 약속 있음/없음 조회는 사서함 사용자의 위치를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-382">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="05b3d-383">약속 있음/없음 조회에서는 여러 리디렉션이 추적 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-383">Free/Busy lookups will not chase multiple redirects.</span></span> 
 
<span data-ttu-id="05b3d-384">**팀 채팅 폴더 콘텐츠가 교차 테 넌 트를 마이그레이션 하나요?**</span><span class="sxs-lookup"><span data-stu-id="05b3d-384">**Does the Teams chat folder content migrate cross-tenant?**</span></span> 

<span data-ttu-id="05b3d-385">아니요, 팀 채팅 폴더 콘텐츠가 교차 테 넌 트를 마이그레이션하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-385">No, the Teams chat folder content does not migrate cross-tenant.</span></span> 
 
<span data-ttu-id="05b3d-386">**내 온 보 딩 및 오프 보 딩 이동이 아니라 테 넌 트 이동의 이동만 표시 하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="05b3d-386">**How can I see just moves that are cross-tenant moves, not my onboarding and offboarding moves?**</span></span>

<span data-ttu-id="05b3d-387">`-flags`매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-387">Use the `-flags` parameter.</span></span> <span data-ttu-id="05b3d-388">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-388">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
<span data-ttu-id="05b3d-389">**테스트에 사용 되는 특성을 복사 하는 예제 스크립트를 제공할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="05b3d-389">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="05b3d-390">샘플-보증 없음</span><span class="sxs-lookup"><span data-stu-id="05b3d-390">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="05b3d-391">이 스크립트는 원본 사서함 (원본 값 가져오기)과 대상 온-프레미스 Active Directory 도메인 서비스 (ADUser 개체 스탬프 지정)에 대 한 연결을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-391">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="05b3d-392">원본에 소송 또는 단일 항목 복구가 사용 하도록 설정 되어 있는 경우 대상 계정에서이를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-392">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="05b3d-393">이렇게 하면 대상 계정의 휴지통 크기가 100 GB로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-393">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="05b3d-394">**사서함을 이동한 후 제 1 일에 Outlook에 액세스 하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="05b3d-394">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="05b3d-395">한 테 넌 트가 도메인을 소유할 수 있으므로 사서함 이동이 완료 되 면 이전 주 SMTPAddress 대상 테 넌 트의 사용자에 게 연결 되지 않습니다. 새 테 넌 트와 연결 된 도메인만</span><span class="sxs-lookup"><span data-stu-id="05b3d-395">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="05b3d-396">Outlook에서는 사용자 새 UPN을 사용 하 여 서비스를 인증 하며, Outlook 프로필에서는 대상 시스템의 사서함과 일치 하도록 레거시 기본 SMTPAddress를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-396">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="05b3d-397">레거시 주소가 대상 시스템에 없으므로 outlook 프로필이 연결 되지 않아 새로 이동한 사서함을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-397">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="05b3d-398">이 초기 배포의 경우 사용자는 새 UPN, 기본 SMTP 주소 및 다시 동기화 OST 콘텐츠를 사용 하 여 프로필을 다시 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-398">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="05b3d-399">사용자가 완료를 위해 일괄 처리 하도록 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-399">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="05b3d-400">Outlook 클라이언트 프로필을 만들고 이후 OST 및 OAB 파일을 클라이언트에 다운로드 하는 경우 네트워크 사용률과 용량을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-400">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="05b3d-401">**테 넌 트 이동을 설정 하거나 완료 하려면 어떤 Exchange RBAC 역할이 필요 합니까?**</span><span class="sxs-lookup"><span data-stu-id="05b3d-401">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="05b3d-402">사서함 이동을 실행할 때 위임 된 의무의 가정을 기반으로 하는 역할 매트릭스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-402">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="05b3d-403">현재 다음과 같은 두 가지 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-403">Currently, two roles are required:</span></span>  

- <span data-ttu-id="05b3d-404">첫 번째 역할은 테 넌 트/조직 경계에서 들어오고 외부로 콘텐츠를 이동할 수 있는 권한을 설정 하는 일회성 설치 작업에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-404">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="05b3d-405">조직 제어에서 데이터를 이동 하는 것이 모든 회사에서 중요 한 관심사 이기 때문에, 조직 관리자 (OrgAdmin)에 게 할당 된 가장 높은 역할이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-405">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="05b3d-406">이 역할은 원격 조직과의-MailboxMoveCapability을 정의 하는 새 New-organizationrelationship를 변경 하거나 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-406">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="05b3d-407">MailboxMoveCapability 설정을 변경할 수 있는 OrgAdmin 있고, OrganizationRelationhip의 기타 특성을 페더레이션 공유 관리자가 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-407">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="05b3d-408">실제 move 명령을 실행 하는 역할은 하위 수준 기능으로 위임 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-408">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="05b3d-409">사서함 이동 역할에는 매개 변수를 사용 하 여 조직 외부로 또는 외부에서 사서함을 이동 하는 기능이 할당 됩니다 `-RemoteTenant` .</span><span class="sxs-lookup"><span data-stu-id="05b3d-409">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="05b3d-410">**어떤 방법으로 변환 된 사서함에서 targetAddress (TargetDeliveryDomain)에 대해 선택한 SMTP 주소를 어떻게 지정 하나요?**</span><span class="sxs-lookup"><span data-stu-id="05b3d-410">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="05b3d-411">MRS를 사용 하 여 Exchange 사서함 이동 대상 개체에 proxyAddress (전자 메일 주소)를 일치 시켜 MailUser로 변환할 때 원본 사서함에서 targetAddress를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-411">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="05b3d-412">이 프로세스에서는 이동 명령에 전달 된-TargetDeliveryDomain 값을 사용 하 여 대상 쪽에서 해당 도메인에 대해 일치 하는 프록시를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-412">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="05b3d-413">일치 하는 항목을 찾은 경우 일치 하는 proxyAddress는 변환 된 사서함 (now MailUser) 개체에서 ExternalEmailAddress (targetAddress)를 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-413">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="05b3d-414">**사서함 사용 권한을 전환 하는 방법**</span><span class="sxs-lookup"><span data-stu-id="05b3d-414">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="05b3d-415">사서함 사용 권한에는 대신 보내기 및 사서함 액세스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-415">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="05b3d-416">대신 보내기 (AD: publicDelegates)는 사용자의 사서함에 대 한 액세스 권한이 있는 받는 사람의 DN을 대리인으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-416">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="05b3d-417">이 값은 Active Directory에 저장 되며 사서함 전환의 일부로 현재 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-417">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="05b3d-418">원본 사서함에 publicDelegates 설정 된 경우에는 명령을 사용 하 여 대상 환경에서 MEU to Mailbox 변환이 완료 되 면 대상 사서함에 publicDelegates을 다시 스탬프 해야 합니다 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` .</span><span class="sxs-lookup"><span data-stu-id="05b3d-418">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment using the `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` command.</span></span> 
 
- <span data-ttu-id="05b3d-419">사서함에 저장 된 사서함 사용 권한은 주 서버와 대리인이 모두 대상 시스템으로 이동 될 때 사서함과 함께 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-419">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="05b3d-420">예를 들어 사용자 TestUser_7에는 테 넌 트 SourceCompany.onmicrosoft.com의 사서함 TestUser_8에 대 한 FullAccess 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-420">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="05b3d-421">사서함 이동이 TargetCompany.onmicrosoft.com으로 완료 된 후에는 대상 디렉터리에 동일한 사용 권한이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-421">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="05b3d-422">원본 및 대상 테 넌 트에서 TestUser_7에 대 한 *add-mailboxpermission* 를 사용 하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-422">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="05b3d-423">Exchange cmdlet에는 원본 및 대상에 따라 접두사가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-423">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="05b3d-424">다음은 이동 하기 전의 사서함 사용 권한 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-424">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="05b3d-425">다음은 이동 후의 사서함 사용 권한 출력에 대 한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-425">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="05b3d-426">테 넌 트 사서함 및 일정 사용 권한은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-426">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="05b3d-427">이러한 연결 된 사서함이 원본 테 넌 트에서 동시에 전환 되도록 주체와 대리인을 통합 일괄 처리로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-427">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 
 
## <a name="known-issues"></a><span data-ttu-id="05b3d-428">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="05b3d-428">Known issues</span></span> 

-  <span data-ttu-id="05b3d-429">**문제: 자동으로 확장 된 보관 함을 마이그레이션할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="05b3d-429">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="05b3d-430">테 넌 트 마이그레이션 기능은 특정 사용자에 대 한 기본 사서함 및 보관 사서함의 마이그레이션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-430">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="05b3d-431">원본 사용자가 보관 사서함을 두 개 이상 자동으로 확장 한 경우에는 해당 기능을 통해 추가 보관 함을 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-431">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="05b3d-432">**문제: 소유 하지 않은 smtp proxyAddress block을 사용 하는 클라우드 MailUsers MRS가 background를 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="05b3d-432">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="05b3d-433">대상 테 넌 트 MailUser 개체를 만들 때 모든 SMTP 프록시 주소가 대상 테 넌 트 조직에 속하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-433">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="05b3d-434">로컬 테 넌 트에 속하지 않은 대상 메일 사용자에 게 SMTP proxyAddress가 있으면 MailUser를 Mailbox로 변환 하는 것이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-434">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="05b3d-435">이는 사서함 개체가 테 넌 트가 신뢰할 수 있는 도메인 (테 넌 트에 의해 요구 되는 도메인)에서 메일을 보내기만 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-435">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 
- 
   - <span data-ttu-id="05b3d-436">Azure AD Connect를 사용 하 여 온-프레미스에서 사용자를 동기화 하는 경우 온-프레미스 MailUser 개체는 사서함이 있는 원본 테 넌 트를 가리키는 ExternalEmailAddress (laran@contoso onmicrosoft.com)를 제공 하 \. 고 PrimarySMTPAddress를 대상 테 넌 트 (Lara.Newton@northwind com)에 있는 도메인으로 스탬프 처리 합니다 \. .</span><span class="sxs-lookup"><span data-stu-id="05b3d-436">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso\.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind\.com).</span></span> <span data-ttu-id="05b3d-437">이러한 값은 테 넌 트에서 동기화 되 고 적절 한 메일 사용자가 프로 비전 되어 마이그레이션 준비가 완료 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-437">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="05b3d-438">예제 개체는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-438">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="05b3d-439">EmailAddresses/proxyAddresses 배열에 *contoso. onmicrosoft \. com* 주소가 *없습니다* .</span><span class="sxs-lookup"><span data-stu-id="05b3d-439">The *contoso.onmicrosoft\.com* address is *not* present in the EmailAddresses/proxyAddresses array.</span></span>

- <span data-ttu-id="05b3d-440">**문제: "external" 기본 SMTP 주소가 있는 MailUser 개체를 수정/다시 설정 하 여 "내부" 회사에 요청한 도메인**</span><span class="sxs-lookup"><span data-stu-id="05b3d-440">**Issue: MailUser objects with “external” primary SMTP addresses are modified/reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="05b3d-441">MailUser 개체는 비로컬 사서함에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-441">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="05b3d-442">테 넌 트 사서함 마이그레이션의 경우에는 MailUser 개체를 사용 하 여 원본 사서함 (대상 조직의 관점) 또는 대상 사서함 (원본 조직의 관점)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-442">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="05b3d-443">MailUsers에는 \@ \. 디렉터리에 있는 사서함 사용자의 표시 된 smtp 주소를 나타내는 실제 사서함 (proxytest fabrikam onmicrosoft.com) 및 primarysmtp 주소의 smtp 주소를 가리키는 ExternalEmailAddress (targetAddress)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-443">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest\@fabrikam\.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="05b3d-444">일부 조직에서는 기본 SMTP 주소를 로컬 테 넌 트 (예: contoso.com가 아닌 fabrikam.com)가 소유 하는 주소가 아닌 외부 SMTP 주소로 표시 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-444">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="05b3d-445">그러나 Exchange 서비스 계획 개체가 라이선스 작업을 통해 MailUser에 적용 되 면 기본 SMTP 주소가 로컬 조직에서 확인 된 도메인 (contoso.com)으로 표시 되도록 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-445">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="05b3d-446">다음과 같은 두 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-446">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="05b3d-447">Exchange 서비스 계획이 MailUser에 적용 되 면 Azure AD 프로세스는 로컬 조직이 다른 테 넌 트에서 메일을 보내거나 스푸핑 또는 메일을 보낼 수 없도록 하기 위해 프록시 스크러빙을 강제로 적용 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-447">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="05b3d-448">로컬 조직에서 주소를 확인 하지 않으면 이러한 서비스 계획이 포함 된 받는 사람 개체의 모든 SMTP 주소가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-448">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="05b3d-449">예제의 경우와 마찬가지로, Fabikam \. com 도메인은 contoso onmicrosoft.com 테 넌 트에 의해 확인 되지 않으므로 \. 스크러빙은 해당 fabrikam com 도메인을 제거 합니다 \. .</span><span class="sxs-lookup"><span data-stu-id="05b3d-449">As is the case in the example, the Fabikam\.com domain is NOT verified by the contoso\.onmicrosoft.com tenant, so the scrubbing removes that fabrikam\.com domain.</span></span> <span data-ttu-id="05b3d-450">이 외부 도메인을 MailUser에 유지 하려면 마이그레이션 이전 또는 마이그레이션 후에 해당 사용자에 게 예상 되는 외부 브랜딩을 적용 되도록 이동이 완료 된 후 또는 이동 하기 전에 라이선스를 제거 하도록 마이그레이션 프로세스를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-450">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="05b3d-451">메일 서비스에 영향을 주지 않도록 사서함 개체의 사용권이 적절 한지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-451">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="05b3d-452">Contoso onmicrosoft.com 테 넌 트의 MailUser에서 서비스 요금제를 제거 하는 예제 스크립트는 \. 여기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-452">An example script to remove the service plans on a MailUser in the Contoso\.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="05b3d-453">지정 된 ServicePlans 집합의 결과가 여기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-453">Results in the set of ServicePlans assigned are shown here.</span></span>

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       <span data-ttu-id="05b3d-454">사용자의 PrimarySMTPAddress 더 이상 scrubbed 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-454">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="05b3d-455">Fabrikam.com 도메인은 contoso.onmicrosoft.com 테 넌 트에서 소유 되지 않으며 디렉터리에 표시 된 기본 SMTP 주소로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-455">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="05b3d-456">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-456">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="05b3d-457">MsExchRemoteRecipientType가 8 (DeprovisionMailbox)로 설정 되 면 대상 테 넌 트로 마이그레이션되는 온-프레미스 MailUsers의 경우 Azure의 프록시 스크러빙 논리는 소유 하지 않는 도메인을 제거 하 고 primarySMTP를 소유한 도메인으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-457">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="05b3d-458">온-프레미스 MailUser에서 msExchRemoteRecipientType를 지우면 프록시 삭제 논리가 더 이상 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-458">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="05b3d-459">다음은 Exchange Online을 포함 하는 가능한 서비스 계획의 전체 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="05b3d-459">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="05b3d-460">이름</span><span class="sxs-lookup"><span data-stu-id="05b3d-460">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="05b3d-461">고급 eDiscovery 저장소 (500GB)</span><span class="sxs-lookup"><span data-stu-id="05b3d-461">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="05b3d-462">고객 Lockbox</span><span class="sxs-lookup"><span data-stu-id="05b3d-462">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="05b3d-463">데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="05b3d-463">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="05b3d-464">Exchange Enterprise CAL Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="05b3d-464">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="05b3d-465">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="05b3d-465">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="05b3d-466">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="05b3d-466">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="05b3d-467">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="05b3d-467">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="05b3d-468">Exchange Online (계획 1)</span><span class="sxs-lookup"><span data-stu-id="05b3d-468">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="05b3d-469">Exchange Online (계획 2)</span><span class="sxs-lookup"><span data-stu-id="05b3d-469">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="05b3d-470">Exchange Online용 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="05b3d-470">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="05b3d-471">Exchange Server용 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="05b3d-471">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="05b3d-472">Exchange Online 비활성 사용자 추가 기능</span><span class="sxs-lookup"><span data-stu-id="05b3d-472">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="05b3d-473">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="05b3d-473">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="05b3d-474">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="05b3d-474">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="05b3d-475">Exchange Online 요금제 1</span><span class="sxs-lookup"><span data-stu-id="05b3d-475">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="05b3d-476">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="05b3d-476">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="05b3d-477">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="05b3d-477">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="05b3d-478">정보 장벽</span><span class="sxs-lookup"><span data-stu-id="05b3d-478">Information Barriers</span></span>                              |
   | <span data-ttu-id="05b3d-479">Office 365에 대 한 정보 보호-Premium</span><span class="sxs-lookup"><span data-stu-id="05b3d-479">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="05b3d-480">Office 365에 대 한 정보 보호-표준</span><span class="sxs-lookup"><span data-stu-id="05b3d-480">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="05b3d-481">MyAnalytics에서의 정보</span><span class="sxs-lookup"><span data-stu-id="05b3d-481">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="05b3d-482">Microsoft 365 고급 감사</span><span class="sxs-lookup"><span data-stu-id="05b3d-482">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="05b3d-483">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="05b3d-483">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="05b3d-484">Microsoft 비즈니스 센터</span><span class="sxs-lookup"><span data-stu-id="05b3d-484">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="05b3d-485">Microsoft MyAnalytics (Full)</span><span class="sxs-lookup"><span data-stu-id="05b3d-485">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="05b3d-486">Office 365 고급 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="05b3d-486">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="05b3d-487">Microsoft Defender for Office 365 (요금제 1)</span><span class="sxs-lookup"><span data-stu-id="05b3d-487">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="05b3d-488">Microsoft Defender for Office 365 (요금제 2)</span><span class="sxs-lookup"><span data-stu-id="05b3d-488">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="05b3d-489">Office 365 권한 있는 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="05b3d-489">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="05b3d-490">Outlook Customer Manager</span><span class="sxs-lookup"><span data-stu-id="05b3d-490">Outlook Customer Manager</span></span>                          |
   | <span data-ttu-id="05b3d-491">Office 365의 Premium 암호화</span><span class="sxs-lookup"><span data-stu-id="05b3d-491">Premium Encryption in Office 365</span></span>                  |
   || 
 
