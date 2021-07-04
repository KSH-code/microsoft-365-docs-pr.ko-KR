---
title: 교차 테넌트 사서함 마이그레이션
description: 테넌트 또는 Microsoft 365 Office 365 이동하는 방법
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
ms.openlocfilehash: 018c47076642d4ce51340aed5fcb25c1d25c6b4f
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289166"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="66204-103">테넌트 간 사서함 마이그레이션(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="66204-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="66204-104">이전에는 Exchange Online 테넌트가 동일한 Exchange Online 서비스의 다른 테넌트로 사서함을 이동해야 하는 경우 온-프레미스로 사서함을 완전히 오프보드한 다음 새 테넌트에 온보드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="66204-105">새로운 테넌트 간 사서함 마이그레이션 기능을 사용하면 원본 및 대상 테넌트의 테넌트 관리자가 모든 테넌트 간에 사서함을 이동할 수 있으며, 해당 테넌트의 인프라 종속성은 최소한의 수준으로 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="66204-106">이렇게 하여 사서함을 오프보드하고 온보드할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="66204-107">일반적으로 인수 또는 매입 중에 사용자와 콘텐츠를 새 테넌트로 이동하는 능력이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="66204-108">대상 테넌트 관리자가 이동을 실행하면 온-프레미스에서 클라우드 온보더링 마이그레이션과 유사하게 끌어오기 이동이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="66204-109">테넌트 간 Exchange 사서함 이동은 테넌트 관리자가 완벽하게 셀프 서비스하여 사용자를 새 조직으로 전환하는 데 필요한 더 큰 워크플로로 스크립팅할 수 있는 잘 알려진 인터페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="66204-110">관리자는 사서함 이동 관리 역할을 통해 사용할 수 있는 cmdlet을 사용하여 테넌트 간 이동을 실행할 `New-MigrationBatch` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="66204-111">이동 프로세스에는 사서함 동기화 및 완료 중에 테넌트 권한 부여 검사가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span>

<span data-ttu-id="66204-112">테넌트 간 이동을 Exchange Online 특정 특성으로 표시된 MailUsers로 대상 테넌트 Exchange Online 시스템에 사용자 마이그레이션이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="66204-113">대상 테넌트에서 제대로 설정되지 않은 사용자에 대해 시스템이 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>

<span data-ttu-id="66204-114">이동이 완료되면 원본 시스템 사서함이 MailUser로 변환되어 targetAddress(Exchange의 ExternalEmailAddress로 표시)는 대상 테넌트에 대한 라우팅 주소로 스탬프가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="66204-115">이 프로세스는 원본 테넌트에 레거시 MailUser를 그대로 남겨두고 공조 및 메일 라우팅을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="66204-116">비즈니스 프로세스에서 허용하는 경우 원본 테넌트가 원본 MailUser를 제거하거나 메일 연락처로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span>

<span data-ttu-id="66204-117">크로스 테넌트 Exchange 하이브리드 또는 클라우드의 테넌트 또는 둘의 임의 조합에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="66204-118">이 문서에서는 테넌트 간 사서함 이동 프로세스에 대해 설명하고 콘텐츠 이동을 위해 원본 및 대상 테넌트를 준비하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="66204-119">원본 및 대상 테넌트 준비</span><span class="sxs-lookup"><span data-stu-id="66204-119">Preparing source and target tenants</span></span>

<span data-ttu-id="66204-120">크로스 테넌트 Exchange 마이그레이션 기능을 사용하려면 테넌트 간 마이그레이션을 위한 권한 부여 및 스위핑이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="66204-121">이제 테넌트 관리자는 Azure Enterprise 응용 프로그램 및 Key Vault 저장소 솔루션을 사용하여 한 테넌트에서 다른 테넌트로의 Exchange Online 사서함 마이그레이션의 권한 부여 및 Exchange Online 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="66204-122">테넌트 간 사서함 이동은 초대 및 동의 모델을 지원하여 테넌트 쌍 간의 인증에 Azure Active Directory(Azure AD) 응용 프로그램을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="66204-123">조직 관계 및 마이그레이션 끝점과 같은 추가 구성 요소도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="66204-124">이 섹션에는 대상 디렉터리에서 MailUser 사용자 개체를 준비하는 데 필요한 특정 단계가 포함되어 있지 않으며 마이그레이션 일괄 처리를 제출하기 위한 예제 명령도 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="66204-125">이 정보는 마이그레이션을 위해 대상 [사용자 개체 준비를](#prepare-target-user-objects-for-migration) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66204-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66204-126">필수 조건</span><span class="sxs-lookup"><span data-stu-id="66204-126">Prerequisites</span></span>

<span data-ttu-id="66204-127">테넌트 간 사서함 이동 기능을 사용하려면 [Azure Key Vault가](/azure/key-vault/basic-concepts) 테넌트 쌍별 Azure 응용 프로그램을 설정하여 한 테넌트에서 다른 테넌트로의 사서함 마이그레이션을 인증하고 권한을 부여하는 데 사용되는 인증서/비밀을 안전하게 저장하고 액세스하고 테넌트 간에 인증서/비밀을 공유하기 위한 요구 사항을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span>

<span data-ttu-id="66204-128">시작하기 전에 Azure Key Vault, 사서함 응용 프로그램 이동, EXO 마이그레이션 끝점 및 EXO 조직 관계를 구성하기 위해 배포 스크립트를 실행하기 위해 필요한 사용 권한이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="66204-129">일반적으로 전역 관리자에게는 모든 구성 단계를 수행할 수 있는 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="66204-130">또한 설치를 실행하기 전에 원본 테넌트의 메일 사용이 가능한 보안 그룹이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="66204-131">이러한 그룹은 원본(또는 리소스라고도 하는) 테넌트에서 대상 테넌트로 이동할 수 있는 사서함 목록의 범위를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="66204-132">이렇게 하면 원본 테넌트 관리자가 이동해야 하는 특정 사서함 집합을 제한하거나 범위를 지정하여 의도하지 않은 사용자가 마이그레이션되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="66204-133">중첩된 그룹은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-133">Nested groups are not supported.</span></span>

<span data-ttu-id="66204-134">또한 해당 테넌트 ID를 얻기 위해 신뢰할 수 있는 파트너 회사(사서함을 이동하는 Microsoft 365 통신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="66204-135">이 테넌트 ID는 조직 관계 필드에 `DomainName` 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="66204-136">구독의 테넌트 ID를 얻습니다. 구독에 로그인하여 Microsoft 365 관리 센터 로 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="66204-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="66204-137">테넌트 ID 속성의 복사 아이콘을 클릭하여 클립보드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="66204-138">다음은 프로세스의 작동 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="사서함 마이그레이션을 위한 테넌트 준비":::

<span data-ttu-id="66204-140">[이 이미지의 더 큰 버전을 참조합니다.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)</span><span class="sxs-lookup"><span data-stu-id="66204-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
-->

### <a name="prepare-tenants"></a><span data-ttu-id="66204-141">테넌트 준비</span><span class="sxs-lookup"><span data-stu-id="66204-141">Prepare tenants</span></span>

<span data-ttu-id="66204-142">높은 수준에서는 설치 스크립트를 실행할 때 다음 구성 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="66204-143">대상 테넌트 준비:</span><span class="sxs-lookup"><span data-stu-id="66204-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="66204-144">기존 Azure 리소스 그룹을 제공하지 않은 경우 새 Azure 리소스 그룹(SCRIPT)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66204-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="66204-145">기존 Key Vault가 제공되지 않은 경우 새 키 자격 증명 모음(SCRIPT)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66204-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="66204-146">SCRIPT(사서함 마이그레이션 응용 프로그램Office 365 Exchange Online 새 액세스 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66204-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="66204-147">SCRIPT(마이그레이션 응용 프로그램)에 대한 비밀을 보유하기 위해 새 인증서(또는 지정된 경우 기존 인증서)가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66204-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="66204-148">새 Azure AD 응용 프로그램(SCRIPT)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66204-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="66204-149">인증서/비밀이 마이그레이션 응용 프로그램(SCRIPT)에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="66204-150">사서함 마이그레이션 권한이 응용 프로그램(SCRIPT)에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="66204-151">배포 스크립트는 대상 관리자가 자신의 응용 프로그램(SCRIPT)에 동의할 때까지 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="66204-152">대상 테넌트 관리자는 응용 프로그램(MANUAL)에 부여된 사용 권한에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="66204-153">조직 관계가 대상 테넌트(SCRIPT)에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66204-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="66204-154">마이그레이션 끝점은 대상 테넌트(SCRIPT)로 사서함을 끌어오기 위해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66204-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="66204-155">원본 테넌트 준비:</span><span class="sxs-lookup"><span data-stu-id="66204-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="66204-156">원본 테넌트 관리자는 대상 테넌트(MANUAL)에서 사서함 마이그레이션 응용 프로그램 초대에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="66204-157">원본 테넌트 관리자는 마이그레이션 응용 프로그램(MANUAL)에서 이동할 수 있는 사서함 목록을 포함하도록 테넌트에 메일 사용이 가능한 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66204-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="66204-158">사서함 마이그레이션 응용 프로그램을 지정하는 대상 테넌트에 조직 관계가 만들어지며, OAuth 확인을 통해 SCRIPT(이동 요청)를 수락해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="66204-159">대상 테넌트 관리자에 대한 단계별 지침</span><span class="sxs-lookup"><span data-stu-id="66204-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="66204-160">SetupCrossTenantRelationshipForTargetTenant.ps1 리포지토리에서 대상 테넌트 설정에 대한 GitHub [스크립트를 다운로드합니다.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="66204-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span>
2. <span data-ttu-id="66204-161">스크립트를 실행할 컴퓨터에 SetupCrossTenantRelationshipForTargetTenant.ps1(스크립트)를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="66204-162">대상 테넌트에 대한 원격 PowerShell 연결을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="66204-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="66204-163">Azure Key Vault 저장소 및 인증서, 사서함 응용 프로그램 이동, EXO 마이그레이션 끝점 및 EXO 조직 관계를 구성하기 위해 배포 스크립트를 실행하기 위해 필요한 사용 권한이 있는지도 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="66204-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="66204-164">파일 폴더 디렉터리를 스크립트 위치로 변경하거나 스크립트가 현재 원격 PowerShell 세션의 위치에 저장되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="66204-165">다음 매개 변수와 값으로 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-165">Run the script with the following parameters and values.</span></span>

   |<span data-ttu-id="66204-166">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66204-166">Parameter</span></span>|<span data-ttu-id="66204-167">값</span><span class="sxs-lookup"><span data-stu-id="66204-167">Value</span></span>|<span data-ttu-id="66204-168">필수 또는 선택 사항</span><span class="sxs-lookup"><span data-stu-id="66204-168">Required or Optional</span></span>
   |---|---|---|
   |<span data-ttu-id="66204-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="66204-169">-TargetTenantDomain</span></span>|<span data-ttu-id="66204-170">대상 테넌트 도메인(예: fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="66204-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span>|<span data-ttu-id="66204-171">필수</span><span class="sxs-lookup"><span data-stu-id="66204-171">Required</span></span>|
   |<span data-ttu-id="66204-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="66204-172">-ResourceTenantDomain</span></span>|<span data-ttu-id="66204-173">원본 테넌트 도메인(예: contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="66204-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span>|<span data-ttu-id="66204-174">필수</span><span class="sxs-lookup"><span data-stu-id="66204-174">Required</span></span>|
   |<span data-ttu-id="66204-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="66204-175">-ResourceTenantAdminEmail</span></span>|<span data-ttu-id="66204-176">원본 테넌트 관리자의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="66204-177">대상 관리자가 보낸 사서함 마이그레이션 응용 프로그램 사용에 동의하는 원본 테넌트 관리자입니다. 이 관리자는 응용 프로그램에 대한 전자 메일 초대를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span>|<span data-ttu-id="66204-178">필수</span><span class="sxs-lookup"><span data-stu-id="66204-178">Required</span></span>|
   |<span data-ttu-id="66204-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="66204-179">-ResourceTenantId</span></span>|<span data-ttu-id="66204-180">원본 테넌트 조직 ID(GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-180">Source tenant organization ID (GUID).</span></span>|<span data-ttu-id="66204-181">필수</span><span class="sxs-lookup"><span data-stu-id="66204-181">Required</span></span>|
   |<span data-ttu-id="66204-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="66204-182">-SubscriptionId</span></span>|<span data-ttu-id="66204-183">리소스를 만드는 데 사용할 Azure 구독입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-183">The Azure subscription to use for creating resources.</span></span>|<span data-ttu-id="66204-184">필수</span><span class="sxs-lookup"><span data-stu-id="66204-184">Required</span></span>|
   |<span data-ttu-id="66204-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="66204-185">-ResourceGroup</span></span>|<span data-ttu-id="66204-186">키 자격 증명 모음을 포함하거나 포함할 Azure 리소스 그룹 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-186">Azure resource group name that contains or will contain the Key Vault.</span></span>|<span data-ttu-id="66204-187">필수</span><span class="sxs-lookup"><span data-stu-id="66204-187">Required</span></span>|
   |<span data-ttu-id="66204-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="66204-188">-KeyVaultName</span></span>|<span data-ttu-id="66204-189">사서함 마이그레이션 응용 프로그램 인증서/비밀을 저장할 Azure Key Vault 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span>|<span data-ttu-id="66204-190">필수</span><span class="sxs-lookup"><span data-stu-id="66204-190">Required</span></span>|
   |<span data-ttu-id="66204-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="66204-191">-CertificateName</span></span>|<span data-ttu-id="66204-192">키 자격 증명 모음에서 인증서를 생성하거나 검색할 때의 인증서 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-192">Certificate name when generating or searching for certificate in key vault.</span></span>|<span data-ttu-id="66204-193">필수</span><span class="sxs-lookup"><span data-stu-id="66204-193">Required</span></span>|
   |<span data-ttu-id="66204-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="66204-194">-CertificateSubject</span></span>|<span data-ttu-id="66204-195">Azure Key Vault 인증서 주체 이름(예: CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="66204-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span>|<span data-ttu-id="66204-196">필수</span><span class="sxs-lookup"><span data-stu-id="66204-196">Required</span></span>|
   |<span data-ttu-id="66204-197">-AzureResourceLocation</span><span class="sxs-lookup"><span data-stu-id="66204-197">-AzureResourceLocation</span></span>|<span data-ttu-id="66204-198">Azure 리소스 그룹 및 키 자격 증명 모음의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-198">The location of the Azure resource group and key vault.</span></span>|<span data-ttu-id="66204-199">필수</span><span class="sxs-lookup"><span data-stu-id="66204-199">Required</span></span>|
   |<span data-ttu-id="66204-200">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="66204-200">-ExistingApplicationId</span></span>|<span data-ttu-id="66204-201">이미 만들어진 경우 사용할 메일 마이그레이션 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-201">Mail migration application to use if one was already created.</span></span>|<span data-ttu-id="66204-202">선택</span><span class="sxs-lookup"><span data-stu-id="66204-202">Optional</span></span>|
   |<span data-ttu-id="66204-203">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="66204-203">-AzureAppPermissions</span></span>|<span data-ttu-id="66204-204">사서함 마이그레이션 응용 프로그램에 필요한 사용 권한(예: Exchange 또는 MSGraph(사서함 이동을 위한 Exchange, MSGraph를 사용하여 리소스 테넌트에 동의 링크 초대를 보내기 위한 경우)</span><span class="sxs-lookup"><span data-stu-id="66204-204">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span>|<span data-ttu-id="66204-205">필수</span><span class="sxs-lookup"><span data-stu-id="66204-205">Required</span></span>|
   |<span data-ttu-id="66204-206">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="66204-206">-UseAppAndCertGeneratedForSendingInvitation</span></span>|<span data-ttu-id="66204-207">원본 테넌트 관리자에게 동의 링크 초대를 보내는 데 사용할 마이그레이션을 위해 만든 응용 프로그램을 사용하는 매개 변수입니다. 이 메시지가 없는 경우 대상 관리자의 자격 증명을 사용하여 Azure 초대 관리자에 연결하고 초대를 대상 관리자로 보낼지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-207">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span>|<span data-ttu-id="66204-208">선택</span><span class="sxs-lookup"><span data-stu-id="66204-208">Optional</span></span>|
   |<span data-ttu-id="66204-209">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="66204-209">-KeyVaultAuditStorageAccountName</span></span>|<span data-ttu-id="66204-210">Key Vault의 감사 로그가 저장될 저장소 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-210">The storage account where Key Vault’s audit logs would be stored.</span></span>|<span data-ttu-id="66204-211">선택</span><span class="sxs-lookup"><span data-stu-id="66204-211">Optional</span></span>|
   |<span data-ttu-id="66204-212">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="66204-212">-KeyVaultAuditStorageResourceGroup</span></span>|<span data-ttu-id="66204-213">키 자격 증명 모음 감사 로그를 저장하기 위한 저장소 계정이 포함된 리소스 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-213">The resource group that contains the storage account for storing Key Vault audit logs.</span></span>|<span data-ttu-id="66204-214">선택</span><span class="sxs-lookup"><span data-stu-id="66204-214">Optional</span></span>|
   ||||

    > [!NOTE]
    > <span data-ttu-id="66204-215">스크립트를 실행하기 전에 Azure AD PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-215">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="66204-216">설치 단계는 [여기를](/powershell/azure/install-az-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66204-216">Please refer to [here](/powershell/azure/install-az-ps) for installation steps</span></span>

6. <span data-ttu-id="66204-217">이 스크립트는 일시 중지된 후 이 프로세스 중에 만들어진 Exchange 사서함 마이그레이션 응용 프로그램에 동의하거나 동의할 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-217">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="66204-218">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-218">Here is an example.</span></span>

    ```powershell
    PS C:\PowerShell\> # Note: the below User.Invite.All permission is optional, and will only be used to retrieve access token to send invitation email to source tenant
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureResourceLocation "Brazil Southeast" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - User.Invite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```

7. <span data-ttu-id="66204-219">URL이 원격 PowerShell 세션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-219">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="66204-220">테넌트 동의에 대해 제공된 링크를 복사하여 웹 브라우저에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-220">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="66204-221">전역 관리자 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-221">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="66204-222">다음 화면이 표시된 경우 수락을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66204-222">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="사용 권한 수락 대화 상자":::

9. <span data-ttu-id="66204-224">원격 PowerShell 세션으로 다시 전환하고 Enter를 입력하여 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-224">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="66204-225">스크립트는 나머지 설치 개체를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-225">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="66204-226">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-226">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="66204-227">이제 대상 관리자 설정이 완료되었습니다!</span><span class="sxs-lookup"><span data-stu-id="66204-227">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="66204-228">원본 테넌트 관리자에 대한 단계별 지침</span><span class="sxs-lookup"><span data-stu-id="66204-228">Step-by-step instructions for the source tenant admin</span></span>

1. <span data-ttu-id="66204-229">설치하는 동안 대상 관리자가 지정한 -ResourceTenantAdminEmail로 사서함에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-229">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="66204-230">대상 테넌트에서 전자 메일 초대를 찾은 다음 전자 메일 시작 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66204-230">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="초대를 들은 대화 상자":::

2. <span data-ttu-id="66204-232">**수락을** 선택하여 초대를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-232">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="사용 권한을 수락할 대화 상자":::

   > [!NOTE]
   > <span data-ttu-id="66204-234">이 전자 메일을 수신하지 못하거나 찾을 수 없는 경우 대상 테넌트 관리자가 초대를 수락할 수 있는 직접 URL을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-234">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="66204-235">URL은 대상 테넌트 관리자의 원격 PowerShell 세션의 스크립트에 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-235">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="66204-236">Microsoft 365 관리 센터 또는 원격 PowerShell 세션에서 하나 이상의 메일 사용이 가능한 보안 그룹을 만들어 대상 테넌트가 원본 테넌트에서 대상 테넌트로 끌어오기(이동)할 수 있는 사서함 목록을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-236">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="66204-237">이 그룹을 미리 채우지 않고도 설정 단계(스크립트)를 실행하려면 하나 이상의 그룹을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-237">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="66204-238">중첩 그룹은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-238">Nest groups are not supported.</span></span>

4. <span data-ttu-id="66204-239">원본 테넌트 SetupCrossTenantRelationshipForResourceTenant.ps1 대한 GitHub 스크립트를 다운로드합니다. [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="66204-239">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span>

5. <span data-ttu-id="66204-240">관리자 권한으로 원본 테넌트에 대한 원격 PowerShell 연결을 Exchange.</span><span class="sxs-lookup"><span data-stu-id="66204-240">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="66204-241">전역 관리자 권한은 원본 테넌트 구성에 필요하지 않습니다. Azure 응용 프로그램 만들기 프로세스 때문에 대상 테넌트만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-241">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="66204-242">디렉터리를 스크립트 위치로 변경하거나 스크립트가 현재 원격 PowerShell 세션의 위치에 저장되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-242">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="66204-243">다음 필수 매개 변수와 값을 사용하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-243">Run the script with the following required parameters and values.</span></span>

   |<span data-ttu-id="66204-244">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66204-244">Parameter</span></span>|<span data-ttu-id="66204-245">값</span><span class="sxs-lookup"><span data-stu-id="66204-245">Value</span></span>|
   |---|---|
   |<span data-ttu-id="66204-246">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="66204-246">-SourceMailboxMovePublishedScopes</span></span>|<span data-ttu-id="66204-247">마이그레이션 범위에 있는 ID/사서함에 대해 원본 테넌트에서 만든 메일 사용이 가능한 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-247">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span>|
   |<span data-ttu-id="66204-248">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="66204-248">-ResourceTenantDomain</span></span>|<span data-ttu-id="66204-249">원본 테넌트 도메인 이름(예: contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="66204-249">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span>|
   |<span data-ttu-id="66204-250">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="66204-250">-ApplicationId</span></span>|<span data-ttu-id="66204-251">마이그레이션에 사용되는 응용 프로그램의 Azure 응용 프로그램 ID(GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-251">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="66204-252">Azure Portal(Azure AD, Enterprise 응용 프로그램, 앱 이름, 응용 프로그램 ID)을 통해 제공되거나 초대 전자 메일에 포함된 응용 프로그램 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-252">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>|
   |<span data-ttu-id="66204-253">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="66204-253">-TargetTenantDomain</span></span>|<span data-ttu-id="66204-254">대상 테넌트 도메인 이름(예: fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="66204-254">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span>|
   |<span data-ttu-id="66204-255">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="66204-255">-TargetTenantId</span></span>|<span data-ttu-id="66204-256">대상 테넌트의 테넌트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-256">Tenant ID of the target tenant.</span></span> <span data-ttu-id="66204-257">예를 들어 contoso 테넌트의 Azure AD 테넌트 ID는 onmicrosoft.com \. 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-257">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span>|
   |||

    <span data-ttu-id="66204-258">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-258">Here is an example.</span></span>

    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.
    ```

<span data-ttu-id="66204-259">이제 원본 관리자 설정이 완료되었습니다!</span><span class="sxs-lookup"><span data-stu-id="66204-259">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="66204-260">설치 확인</span><span class="sxs-lookup"><span data-stu-id="66204-260">Verify setup</span></span>

<span data-ttu-id="66204-261">원본 테넌트와 대상 테넌트 둘 다의 조직 관계와 대상의 마이그레이션 끝점이 성공적으로 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-261">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="66204-262">대상 테넌트</span><span class="sxs-lookup"><span data-stu-id="66204-262">Target tenant</span></span>

##### <a name="organization-relationship"></a><span data-ttu-id="66204-263">조직 관계</span><span class="sxs-lookup"><span data-stu-id="66204-263">Organization relationship</span></span>

<span data-ttu-id="66204-264">이 명령을 사용하여 조직 관계 개체가 만들어지며 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="66204-264">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="66204-265">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-265">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound
```

##### <a name="migration-endpoint"></a><span data-ttu-id="66204-266">마이그레이션 끝점</span><span class="sxs-lookup"><span data-stu-id="66204-266">Migration endpoint</span></span>

<span data-ttu-id="66204-267">이 명령을 사용하여 마이그레이션 끝점 개체가 만들어지고 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="66204-267">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="66204-268">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-268">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308
```

#### <a name="source-tenant"></a><span data-ttu-id="66204-269">원본 테넌트</span><span class="sxs-lookup"><span data-stu-id="66204-269">Source tenant</span></span>

##### <a name="organization-relationship"></a><span data-ttu-id="66204-270">조직 관계</span><span class="sxs-lookup"><span data-stu-id="66204-270">Organization relationship</span></span>

<span data-ttu-id="66204-271">이 명령을 사용하여 조직 관계 개체가 만들어지며 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="66204-271">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="66204-272">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-272">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="66204-273">설치 스크립트 확인</span><span class="sxs-lookup"><span data-stu-id="66204-273">Verify Setup Script</span></span>

<span data-ttu-id="66204-274">원본 또는 대상 테넌트 구성 중에 오류가 발생하는 경우 원본 또는 대상 테넌트에 있는 VerifySetup.ps1 스크립트를 실행하여 GitHub 검토할 수 있습니다. [](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="66204-274">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="66204-275">다음은 대상 테넌트에서 VerifySetup.ps1 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-275">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="66204-276">다음은 원본 테넌트의 VerifySetup.ps1 예입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-276">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="66204-277">사서함을 원래 원본으로 다시 이동</span><span class="sxs-lookup"><span data-stu-id="66204-277">Move mailboxes back to the original source</span></span>

<span data-ttu-id="66204-278">사서함을 원래 원본 테넌트로 다시 이동해야 하는 경우 새 원본 테넌트와 새 대상 테넌트에서 동일한 단계 및 스크립트 집합을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-278">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="66204-279">기존 Organization Relationship 개체는 다시 생성되지 않는 업데이트 또는 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-279">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="66204-280">마이그레이션을 위한 대상 사용자 개체 준비</span><span class="sxs-lookup"><span data-stu-id="66204-280">Prepare target user objects for migration</span></span>

<span data-ttu-id="66204-281">테넌트 간 이동을 사용하려면 마이그레이션하는 사용자가 대상 테넌트에 있어야 Exchange Online 시스템(MailUsers)에 특정 특성이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-281">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="66204-282">대상 테넌트에서 제대로 설정되지 않은 사용자에 대해 시스템이 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-282">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="66204-283">다음 섹션에서는 대상 테넌트에 대한 MailUser 개체 요구 사항에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-283">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="66204-284">필수 조건</span><span class="sxs-lookup"><span data-stu-id="66204-284">Prerequisites</span></span>

<span data-ttu-id="66204-285">대상 조직에서 다음과 같은 개체와 특성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-285">You must ensure the following objects and attributes are set in the target organization.</span></span>

1. <span data-ttu-id="66204-286">원본 조직에서 이동하는 사서함의 경우 대상 조직에서 MailUser 개체를 프로비전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-286">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span>

   - <span data-ttu-id="66204-287">Target MailUser에는 원본 사서함에서 이러한 특성이 있어야 합니다. 또는 새 User 개체와 함께 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-287">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="66204-288">ExchangeGUID(원본에서 대상으로 직접 흐름) - 사서함 GUID가 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-288">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="66204-289">이 개체가 대상 개체에 없는 경우 이동 프로세스가 진행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-289">The move process will not proceed if this is not present on target object.</span></span>
      - <span data-ttu-id="66204-290">ArchiveGUID(원본에서 대상으로 직접 흐름) - 보관 GUID가 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-290">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="66204-291">이 개체가 대상 개체에 없는 경우 이동 프로세스가 진행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-291">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="66204-292">이 설정은 원본 사서함이 보관을 사용하도록 설정된 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-292">(This is only required if the source mailbox is Archive enabled).</span></span>
      - <span data-ttu-id="66204-293">LegacyExchangeDN(proxyAddress, "x500: <LegacyExchangeDN> ") – LegacyExchangeDN은 대상 MailUser에 x500: proxyAddress로 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-293">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="66204-294">이 개체가 대상 개체에 없는 경우 이동 프로세스가 진행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-294">The move processes will not proceed if this is not present on the target object.</span></span>
      - <span data-ttu-id="66204-295">UserPrincipalName – UPN이 사용자의 새 ID 또는 대상 회사(예: user@northwindtraders.onmicrosoft.com)에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="66204-295">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span>
      - <span data-ttu-id="66204-296">기본 SMTPAddress – 기본 SMTP 주소가 사용자의 새 회사(예: user@northwind.com)에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="66204-296">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span>
      - <span data-ttu-id="66204-297">TargetAddress/ExternalEmailAddress – MailUser는 원본 테넌트에 호스트된 사용자의 현재 사서함을 참조합니다(예: user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="66204-297">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="66204-298">이 값을 할당할 때 PrimarySMTPAddress도 할당하고 있는지 또는 이 값이 이동 실패의 원인이 될 PrimarySMTPAddress를 설정하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-298">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span>
      - <span data-ttu-id="66204-299">원본 사서함의 레거시 smtp 프록시 주소를 대상 MailUser에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-299">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="66204-300">예를 들어 테넌트 개체의 MEU에 contoso.com 유지 fabrikam.onmicrosoft.com 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-300">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="66204-301">도메인은 하나의 Azure AD 또는 Exchange Online 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-301">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>

     <span data-ttu-id="66204-302">대상  MailUser 개체의 예:</span><span class="sxs-lookup"><span data-stu-id="66204-302">Example **target** MailUser object:</span></span>

     |<span data-ttu-id="66204-303">특성</span><span class="sxs-lookup"><span data-stu-id="66204-303">Attribute</span></span>|<span data-ttu-id="66204-304">값</span><span class="sxs-lookup"><span data-stu-id="66204-304">Value</span></span>|
     |---|---|
     |<span data-ttu-id="66204-305">별칭</span><span class="sxs-lookup"><span data-stu-id="66204-305">Alias</span></span>|<span data-ttu-id="66204-306">라라N</span><span class="sxs-lookup"><span data-stu-id="66204-306">LaraN</span></span>|
     |<span data-ttu-id="66204-307">RecipientType</span><span class="sxs-lookup"><span data-stu-id="66204-307">RecipientType</span></span>|<span data-ttu-id="66204-308">MailUser</span><span class="sxs-lookup"><span data-stu-id="66204-308">MailUser</span></span>|
     |<span data-ttu-id="66204-309">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="66204-309">RecipientTypeDetails</span></span>|<span data-ttu-id="66204-310">MailUser</span><span class="sxs-lookup"><span data-stu-id="66204-310">MailUser</span></span>|
     |<span data-ttu-id="66204-311">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="66204-311">UserPrincipalName</span></span>|<span data-ttu-id="66204-312">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="66204-312">LaraN@northwintraders.onmicrosoft.com</span></span>|
     |<span data-ttu-id="66204-313">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="66204-313">PrimarySmtpAddress</span></span>|<span data-ttu-id="66204-314">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="66204-314">Lara.Newton@northwind.com</span></span>|
     |<span data-ttu-id="66204-315">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="66204-315">ExternalEmailAddress</span></span>|<span data-ttu-id="66204-316">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="66204-316">SMTP:LaraN@contoso.onmicrosoft.com</span></span>|
     |<span data-ttu-id="66204-317">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="66204-317">ExchangeGuid</span></span>|<span data-ttu-id="66204-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="66204-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>|
     |<span data-ttu-id="66204-319">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="66204-319">LegacyExchangeDN</span></span>|<span data-ttu-id="66204-320">/o=First Organization/ou=Exchange 관리 그룹</span><span class="sxs-lookup"><span data-stu-id="66204-320">/o=First Organization/ou=Exchange Administrative Group</span></span>|
     ||<span data-ttu-id="66204-321">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="66204-321">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>|
     |<span data-ttu-id="66204-322">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="66204-322">EmailAddresses</span></span>|<span data-ttu-id="66204-323">x500:/o=first Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="66204-323">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>|
     ||<span data-ttu-id="66204-324">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="66204-324">7273f1f9-Lara</span></span>|
     ||<span data-ttu-id="66204-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="66204-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>|
     ||<span data-ttu-id="66204-326">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="66204-326">SMTP:Lara.Newton@northwind.com</span></span>|
     |||

     <span data-ttu-id="66204-327">원본 **사서함 개체의** 예:</span><span class="sxs-lookup"><span data-stu-id="66204-327">Example **source** Mailbox object:</span></span>

     |<span data-ttu-id="66204-328">특성</span><span class="sxs-lookup"><span data-stu-id="66204-328">Attribute</span></span>|<span data-ttu-id="66204-329">값</span><span class="sxs-lookup"><span data-stu-id="66204-329">Value</span></span>|
     |---|---|
     |<span data-ttu-id="66204-330">별칭</span><span class="sxs-lookup"><span data-stu-id="66204-330">Alias</span></span>|<span data-ttu-id="66204-331">라라N</span><span class="sxs-lookup"><span data-stu-id="66204-331">LaraN</span></span>|
     |<span data-ttu-id="66204-332">RecipientType</span><span class="sxs-lookup"><span data-stu-id="66204-332">RecipientType</span></span>|<span data-ttu-id="66204-333">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="66204-333">UserMailbox</span></span>|
     |<span data-ttu-id="66204-334">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="66204-334">RecipientTypeDetails</span></span>|<span data-ttu-id="66204-335">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="66204-335">UserMailbox</span></span>|
     |<span data-ttu-id="66204-336">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="66204-336">UserPrincipalName</span></span>|<span data-ttu-id="66204-337">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="66204-337">LaraN@contoso.onmicrosoft.com</span></span>|
     |<span data-ttu-id="66204-338">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="66204-338">PrimarySmtpAddress</span></span>|<span data-ttu-id="66204-339">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="66204-339">Lara.Newton@contoso.com</span></span>|
     |<span data-ttu-id="66204-340">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="66204-340">ExchangeGuid</span></span>|<span data-ttu-id="66204-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="66204-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>|
     |<span data-ttu-id="66204-342">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="66204-342">LegacyExchangeDN</span></span>|<span data-ttu-id="66204-343">/o=First Organization/ou=Exchange 관리 그룹</span><span class="sxs-lookup"><span data-stu-id="66204-343">/o=First Organization/ou=Exchange Administrative Group</span></span>|
     ||<span data-ttu-id="66204-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="66204-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>|
     |<span data-ttu-id="66204-345">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="66204-345">EmailAddresses</span></span>|<span data-ttu-id="66204-346">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="66204-346">smtp:LaraN@contoso.onmicrosoft.com</span></span>
     ||<span data-ttu-id="66204-347">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="66204-347">SMTP:Lara.Newton@contoso.com</span></span>|
     |||

   - <span data-ttu-id="66204-348">추가 특성은 하이브리드 쓰기 Exchange 이미 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-348">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="66204-349">그렇지 않은 경우 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-349">If not, they should be included.</span></span>
   - <span data-ttu-id="66204-350">msExchBlockedSendersHash – 클라이언트에서 온라인에서 안전한 수신 및 차단된 보낸 사람 데이터를 다시 프레미스 Active Directory에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-350">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="66204-351">msExchSafeRecipientsHash – 온라인에서 클라이언트에서온-프레미스 Active Directory로 안전한 수신 및 차단된 보낸 사람 데이터를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-351">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="66204-352">msExchSafeSendersHash – 클라이언트에서온-프레미스 Active Directory로 온라인에서 안전하고 차단된 보낸 사람 데이터를 다시 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-352">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="66204-353">원본 사서함이 LitigationHold에 있으며 원본 사서함 복구 가능한 항목 크기가 데이터베이스 기본값(30GB)보다 크면 대상 할당량이 원본 사서함 크기보다 작기 때문에 이동이 진행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-353">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="66204-354">대상 MailUser 개체를 업데이트하여 원본 환경에서 대상으로 ELC 사서함 플래그를 전환할 수 있습니다. 그러면 대상 시스템에서 MailUser의 할당량 확장을 100GB로 트리거하여 대상으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-354">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="66204-355">ELC 플래그를 스탬프 지정하는 명령은 테넌트 관리자에게 노출되지 커넥트 Azure AD 2013을 실행하는 하이브리드 ID에만 이 지침이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-355">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    > [!NOTE]
    > <span data-ttu-id="66204-356">샘플 – 있는 경우 무상 수리</span><span class="sxs-lookup"><span data-stu-id="66204-356">SAMPLE – AS IS, NO WARRANTY</span></span>
    >
    > <span data-ttu-id="66204-357">이 스크립트는 원본 사서함(원본 값을 얻기 위해) 및 대상에 대한 연결(ADUser 개체 스탬프 지정)을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-357">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="66204-358">원본에 소송 또는 단일 항목 복구를 사용하도록 설정한 경우 대상 계정에서 이를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-358">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="66204-359">이렇게 하면 대상 계정의 반지 크기가 100GB로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-359">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}}
    ```

3. <span data-ttu-id="66204-360">비하이블 대상 테넌트는 다음 명령을 실행하여 MailUser 개체에 대한 소송 보류를 사용하도록 설정하고 할당량 을 100GB로 늘려 마이그레이션 전에 MailUsers의 복구 가능한 항목 폴더에 대한 할당량 을 수정할 수 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-360">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="66204-361">이 방식은 하이브리드의 테넌트에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-361">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="66204-362">대상 조직의 사용자는 조직에 적용할 수 있는 적절한 Exchange Online 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-362">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="66204-363">사서함 이동에 앞서 라이선스를 적용할 수 있지만 대상 MailUser가 ExchangeGUID 및 프록시 주소로 올바르게 설정된 후만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-363">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="66204-364">ExchangeGUID가 적용되기 전에 라이선스를 적용하면 대상 조직에 새 사서함이 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-364">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="66204-365">Mailbox 또는 MailUser 개체에 라이선스를 적용하면 확인된 도메인만 EmailAddresses 배열에 포함되도록 모든 SMTP 형식 proxyAddresses가 Exchange 스크러빙됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-365">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span>

5. <span data-ttu-id="66204-366">대상 MailUser에 Source ExchangeGuid와 일치하지 않는 이전 ExchangeGuid가 없는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-366">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="66204-367">대상 MEU에 대해 이전에 사용이 허가되어 사서함을 프로비전한 Exchange Online 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-367">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="66204-368">대상 MailUser가 이전에 사용이 허가되거나 Source ExchangeGuid와 일치하지 않는 ExchangeGuid가 있는 경우 클라우드 MEU를 정리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-368">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="66204-369">이러한 클라우드 MEUS의 경우 를 실행할 수 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-369">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="66204-370">이 프로세스는 다시 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-370">This process is irreversible.</span></span> <span data-ttu-id="66204-371">개체에 softDeleted 사서함이 있는 경우 이 시점 이후에는 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-371">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="66204-372">그러나 선택을 취소한 후 올바른 ExchangeGuid를 대상 개체에 동기화할 수 있으며 MRS는 원본 사서함을 새로 만든 대상 사서함에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-372">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="66204-373">(새 매개 변수에 대한 EHLO 참조 블로그)</span><span class="sxs-lookup"><span data-stu-id="66204-373">(Reference EHLO blog on the new parameter.)</span></span>

    <span data-ttu-id="66204-374">이 명령을 사용하여 이전에 사서함이던 개체를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-374">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="66204-375">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-375">Here is an example.</span></span>

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize

    Name       PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails
    ----       ---------------------------- ------------- --------------------
    John       UserMailbox                  MailUser      MailUser
    ```

    <span data-ttu-id="66204-376">이 명령을 사용하여 소프트 삭제된 사서함의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-376">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="66204-377">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-377">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm
    Are you sure you want to perform this action?
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.
    Do you want to continue?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="66204-378">사서함 마이그레이션 수행</span><span class="sxs-lookup"><span data-stu-id="66204-378">Perform mailbox migrations</span></span>

<span data-ttu-id="66204-379">사서함 마이그레이션의 Exchange 테넌트 간 마이그레이션은 대상 테넌트에서 시작된 마이그레이션 일괄 처리로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-379">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="66204-380">이 방식은 마이그레이션 일괄 처리를 마이그레이션할 때 Exchange 마이그레이션 일괄 처리가 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="66204-380">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span>

### <a name="create-migration-batches"></a><span data-ttu-id="66204-381">마이그레이션 일괄 처리 만들기</span><span class="sxs-lookup"><span data-stu-id="66204-381">Create Migration batches</span></span>

<span data-ttu-id="66204-382">다음은 이동 시작을 위한 마이그레이션 일괄 처리 cmdlet의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-382">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!NOTE]
> <span data-ttu-id="66204-383">CSV 파일의 전자 메일 주소는 원본 테넌트가 아니라 대상 테넌트에 지정된 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-383">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="66204-384">테넌트 간 옵션을 선택할 때 마이그레이션 일괄 처리 Exchange 관리 센터에서 마이그레이션 일괄 처리 전송도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-384">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="66204-385">On-premises MailUsers 업데이트</span><span class="sxs-lookup"><span data-stu-id="66204-385">Update on-premises MailUsers</span></span>

<span data-ttu-id="66204-386">사서함이 원본에서 대상으로 이동한 후 원본 및 대상 모두에 대한 새 targetAddress로 업데이트되는 On-premises 메일 사용자를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-386">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="66204-387">예제에서 이동에 사용되는 targetDeliveryDomain은 에 **contoso.onmicrosoft.com.**</span><span class="sxs-lookup"><span data-stu-id="66204-387">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="66204-388">이 targetAddress로 메일 사용자를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-388">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="66204-389">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="66204-389">Frequently asked questions</span></span>

<span data-ttu-id="66204-390">**이동 후 원본에서 원격Mailboxes를 업데이트해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="66204-390">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="66204-391">예, 원본 테넌트 사서함이 대상 테넌트로 이동할 때 원본의 targetAddress(RemoteRoutingAddress/ExternalEmailAddress)를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-391">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="66204-392">메일 라우팅은 다른 targetAddresses를 사용하는 여러 메일 사용자에 대한 추천을 따를 수 있는 반면, 메일 사용자에 대한 사용 중/사용 중은 사서함 사용자의 위치를 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-392">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="66204-393">무료/사용 중 검색은 여러 리디렉션을 추격하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-393">Free/Busy lookups will not chase multiple redirects.</span></span>

<span data-ttu-id="66204-394">**테넌트 Teams 마이그레이션합니까?**</span><span class="sxs-lookup"><span data-stu-id="66204-394">**Do Teams meetings migrate cross-tenant?**</span></span>

<span data-ttu-id="66204-395">모임이 이동하나 Teams 교차 테넌트에서 항목이 마이그레이션될 때 모임 URL이 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-395">The meetings will move however the Teams meeting URL does not update when items migrate cross-tenant.</span></span> <span data-ttu-id="66204-396">URL이 대상 테넌트에서 유효하지 않은 것이기 때문에 해당 모임을 제거하고 다시 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-396">Since the URL will be invalid in the target tenant you will need to remove and recreate the Teams meetings.</span></span>

<span data-ttu-id="66204-397">**공유 Teams 콘텐츠가 테넌트 간 마이그레이션합니까?**</span><span class="sxs-lookup"><span data-stu-id="66204-397">**Does the Teams chat folder content migrate cross-tenant?**</span></span>

<span data-ttu-id="66204-398">아니요. Teams 폴더 콘텐츠는 테넌트 간 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-398">No, the Teams chat folder content does not migrate cross-tenant.</span></span>

<span data-ttu-id="66204-399">**온보드 및 오프보드 이동이 아니라 테넌트 간 이동인 이동만 볼 수 있는 방법**</span><span class="sxs-lookup"><span data-stu-id="66204-399">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="66204-400">매개 `-flags` 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-400">Use the `-flags` parameter.</span></span> <span data-ttu-id="66204-401">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-401">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"
```

<span data-ttu-id="66204-402">**테스트에 사용되는 특성을 복사하는 예제 스크립트를 제공할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="66204-402">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!NOTE]
> <span data-ttu-id="66204-403">샘플 – 있는 경우 무상 수리</span><span class="sxs-lookup"><span data-stu-id="66204-403">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="66204-404">이 스크립트는 원본 사서함(원본 값을 얻기 위해) 및 대상에 대한 연결(ADUser 개체 스탬프 지정)을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-404">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="66204-405">원본에 소송 또는 단일 항목 복구를 사용하도록 설정한 경우 대상 계정에서 이를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-405">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="66204-406">이렇게 하면 대상 계정의 반지 크기가 100GB로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-406">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit"
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

#################################################################
#Copy the file $outfile to the desktop of the target on-premises
#then run the below to create MEU in Target
#################################################################
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

#################################################################
# On AADSync machine, run AADSync
#################################################################
Start-ADSyncSyncCycle

#AADSync and FWDSync will create the target MEUs in the Target tenant
```

<span data-ttu-id="66204-407">**사용 사서함을 Outlook 1일차에 액세스하는 방법**</span><span class="sxs-lookup"><span data-stu-id="66204-407">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="66204-408">한 테넌트만 도메인을 소유할 수 있는 것이기 때문에 사서함 이동이 완료되면 이전 기본 SMTPAddress가 대상 테넌트의 사용자에게 연결되지 않습니다. 새 테넌트와 연결된 도메인만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-408">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="66204-409">Outlook 새 UPN을 사용하여 서비스에 인증하고 Outlook 프로필은 대상 시스템의 사서함과 일치할 레거시 기본 SMTPAddress를 찾을 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-409">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="66204-410">레거시 주소가 대상 시스템에 있지 않은 경우 Outlook 프로필은 새로 이동된 사서함을 찾기 위해 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-410">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span>

<span data-ttu-id="66204-411">이 초기 배포의 경우 사용자는 새 UPN, 기본 SMTP 주소로 프로필을 다시 작성하고 OST 콘텐츠를 다시 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-411">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span>

> [!NOTE]
> <span data-ttu-id="66204-412">완료를 위해 사용자를 배치할 때 그에 따라 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-412">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="66204-413">클라이언트 프로필을 만들어 후속 OST Outlook OAB 파일을 클라이언트로 다운로드할 때 네트워크 사용률 및 용량을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-413">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span>

<span data-ttu-id="66204-414">**테넌트 Exchange 설정하거나 완료하기 위해 구성원으로 RBAC 역할이 필요한 이유는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="66204-414">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>

<span data-ttu-id="66204-415">사서함 이동을 실행할 때 위임된 업무를 가정한 역할 매트릭스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-415">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="66204-416">현재 다음 두 가지 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-416">Currently, two roles are required:</span></span>

- <span data-ttu-id="66204-417">첫 번째 역할은 테넌트/조직 경계로 또는 외부로 콘텐츠를 이동하는 권한 부여를 설정하는 일회성 설치 작업에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-417">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="66204-418">조직 제어에서 데이터를 이동하는 것은 모든 회사에서 중요한 문제로, 조직 관리자(OrgAdmin)의 가장 높은 할당 역할로 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-418">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="66204-419">이 역할은 원격 조직과의 -MailboxMoveCapability를 정의하는 새 OrganizationRelationship을 변경하거나 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-419">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="66204-420">OrgAdmin만 MailboxMoveCapability 설정을 변경할 수 있는 반면, OrganizationRelationhip의 다른 특성은 페더링 공유 관리자가 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-420">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span>

- <span data-ttu-id="66204-421">실제 이동 명령을 실행하는 역할을 하위 수준 함수로 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-421">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="66204-422">사서함 이동 역할에는 매개 변수를 사용하여 조직 안이나 밖으로 사서함을 이동하는 기능이 `-RemoteTenant` 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-422">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>

<span data-ttu-id="66204-423">**변환된 사서함에서 targetAddress(TargetDeliveryDomain)에 대해 선택한 SMTP 주소를 지정하는 방법(MailUser 변환)?**</span><span class="sxs-lookup"><span data-stu-id="66204-423">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>

<span data-ttu-id="66204-424">Exchange MRS를 사용하여 사서함을 이동하면 대상 개체의 전자 메일 주소(proxyAddress)와 일치하여 MailUser로 변환할 때 원본 원본 사서함의 targetAddress가 만들어지며,</span><span class="sxs-lookup"><span data-stu-id="66204-424">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="66204-425">이 프로세스는 이동 명령에 전달된 -TargetDeliveryDomain 값을 사용하여 대상 쪽에서 해당 도메인에 대한 일치하는 프록시를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-425">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="66204-426">일치하는 항목은 일치하는 proxyAddress를 사용하여 변환된 사서함(현재 MailUser) 개체에 ExternalEmailAddress(targetAddress)를 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-426">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>

<span data-ttu-id="66204-427">**사서함 사용 권한을 전환하는 방법**</span><span class="sxs-lookup"><span data-stu-id="66204-427">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="66204-428">사서함 사용 권한에는 다음을 대신하여 보내기 및 사서함 액세스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-428">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span>

- <span data-ttu-id="66204-429">대신 보내기(AD:publicDelegates)는 사용자 사서함에 대한 액세스 권한이 있는 받는 사람의 DN을 대리인으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-429">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="66204-430">이 값은 Active Directory에 저장되고 현재 사서함 전환의 일부로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-430">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="66204-431">원본 사서함에 publicDelegates가 설정된 경우 를 실행하여 MEU에서 사서함으로의 변환이 대상 환경에서 완료되면 대상 사서함의 publicDelegates를 다시스탬프해야 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-431">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span>

- <span data-ttu-id="66204-432">사서함에 저장된 사용 권한은 보안 주체와 대리인이 모두 대상 시스템으로 이동될 때 사서함과 함께 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-432">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="66204-433">예를 들어 사용자 TestUser_7 테넌트 서버의 사서함 TestUser_8 FullAccess가 SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="66204-433">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="66204-434">사서함 이동이 완료된 TargetCompany.onmicrosoft.com 동일한 사용 권한이 대상 디렉터리에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-434">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="66204-435">원본 테넌트와 대상 테넌트의 TestUser_7 *Get-MailboxPermission을* 사용하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-435">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="66204-436">Exchange cmdlet에는 그에 따라 원본 및 대상이 미리 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-436">Exchange cmdlets are prefixed with source and target accordingly.</span></span>

<span data-ttu-id="66204-437">이동하기 전에 사서함 사용 권한 출력의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-437">Here's an example of the output of the mailbox permission before a move.</span></span>

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```

<span data-ttu-id="66204-438">이동 후 사서함 사용 권한 출력의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-438">Here's an example of the output of the mailbox permission after the move.</span></span>

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```

> [!NOTE]
> <span data-ttu-id="66204-439">테넌트 간 사서함 및 일정 권한은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-439">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="66204-440">이러한 연결된 사서함이 원본 테넌트에서 동시에 전환될 수 있도록 보안 주체와 대리인을 통합 이동 일괄 처리로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-440">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span>

<span data-ttu-id="66204-441">**마이그레이션을 사용하도록 설정하려면 대상 MailUser 프록시 주소에 어떤 X500 프록시를 추가해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="66204-441">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>

<span data-ttu-id="66204-442">테넌트 간 사서함 마이그레이션을 수행하려면 원본 사서함 개체의 LegacyExchangeDN 값을 대상 MailUser 개체의 x500 전자 메일 주소로 스탬프 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-442">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>

<span data-ttu-id="66204-443">예제:</span><span class="sxs-lookup"><span data-stu-id="66204-443">Example:</span></span>

```powershell
LegacyExchangeDN value on source mailbox is:
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara

so the x500 email address to be added to target MailUser object would be:
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara
```

> [!NOTE]
> <span data-ttu-id="66204-444">이 X500 프록시 외에도 원본 사서함의 모든 X500 프록시를 대상의 사서함에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-444">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>

<span data-ttu-id="66204-445">**이동이 작동하지 않는 경우 어디에서 문제 해결을 시작해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="66204-445">**Where do I start troubleshooting if moves do not work?**</span></span>

<span data-ttu-id="66204-446">먼저 VerifySetup.ps1 스크립트를 [실행하고](https://github.com/microsoft/cross-tenant/releases/tag/Preview) GitHub 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-446">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="66204-447">다음은 대상 테넌트에서 VerifySetup.ps1 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-447">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="66204-448">다음은 원본 테넌트에서 VerifySetup.ps1 eExample입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-448">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="66204-449">**원본 테넌트와 대상 테넌트가 동일한 도메인 이름을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="66204-449">**Can the source and target tenant utilize the same domain name?**</span></span>

<span data-ttu-id="66204-450">아니요.</span><span class="sxs-lookup"><span data-stu-id="66204-450">No.</span></span> <span data-ttu-id="66204-451">원본 및 대상 테넌트 도메인 이름은 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-451">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="66204-452">예를 들어 contoso.com 도메인의 원본 도메인과 대상 도메인은 fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="66204-452">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="66204-453">**공유 사서함이 이동하고 계속 작동하나요?**</span><span class="sxs-lookup"><span data-stu-id="66204-453">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="66204-454">예. 그러나 다음 문서에 설명된 바와 같이 스토어 사용 권한만 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-454">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="66204-455">Microsoft Docs | 2013에서 받는 사람에 대한 사용 권한 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="66204-455">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="66204-456">Microsoft 지원 | 전용 사서함에서 사서함 Exchange Outlook 권한을 부여하는 Office 365 방법</span><span class="sxs-lookup"><span data-stu-id="66204-456">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="66204-457">**Azure Key Vault가 필요하며 언제 거래가 이행되는가?**</span><span class="sxs-lookup"><span data-stu-id="66204-457">**Is Azure Key Vault required and when are transactions made?**</span></span>

<span data-ttu-id="66204-458">예. 마이그레이션을 승인하기 위해 키 자격 증명 모음을 사용하여 인증서를 저장하려면 Azure 구독이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-458">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="66204-459">사용자 이름 및 & 사용하여 원본에 인증하는 온보더링 마이그레이션과 달리 테넌트 간 사서함 마이그레이션에서는 OAuth 및 이 인증서를 비밀/자격 증명으로 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-459">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="66204-460">키 자격 증명 모음에 대한 액세스는 모든 사서함 마이그레이션 전체에서 유지 관리되어야 합니다. 이 액세스는 마이그레이션이 시작될 때와 한 번씩, 그리고 증분 동기화 시간 동안 24시간마다 한 번씩 유지 관리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-460">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="66204-461">여기에서 AKV 비용 세부 정보를 검토할 [수 있습니다.](https://azure.microsoft.com/en-us/pricing/details/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="66204-461">You can review AKV costing details [here](https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>

<span data-ttu-id="66204-462">**일괄 처리에 대한 권장 사항이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="66204-462">**Do you have any recommendations for batches?**</span></span>

<span data-ttu-id="66204-463">일괄 처리당 사서함 수가 2,000개를 초과하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-463">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="66204-464">동기화하는 동안 최종 사용자에게 영향이 없는 일괄 처리는 2주 전에 제출하는 것이 좋습니다. 50,000개가 넘는 사서함 수량에 대한 지침이 필요한 경우 2016년 8월에 엔지니어링 피드백 메일 crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="66204-464">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="66204-465">**고객 키와 함께 서비스 암호화를 사용하는 경우 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="66204-465">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="66204-466">이동하기 전에 사서함의 암호가 해독됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-466">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="66204-467">고객 키가 필요한 경우 대상 테넌트에 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="66204-467">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="66204-468">자세한 [내용은 여기를](../compliance/customer-key-overview.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66204-468">See [here](../compliance/customer-key-overview.md) for more information.</span></span>

<span data-ttu-id="66204-469">**예상 마이그레이션 시간은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="66204-469">**What is the estimated migration time?**</span></span>

<span data-ttu-id="66204-470">마이그레이션을 계획하는 데 도움이 [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) 될 수 있도록 여기에 있는 표에는 대량 사서함 마이그레이션 또는 개별 마이그레이션이 완료될 것으로 예상되는 경우에 대한 지침이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-470">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="66204-471">이러한 예상 비용은 이전 고객 마이그레이션에 대한 데이터 분석을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-471">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="66204-472">모든 환경은 고유하기 때문에 정확한 마이그레이션 속도는 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-472">Because every environment is unique, your exact migration velocity may vary.</span></span>

<span data-ttu-id="66204-473">이 기능은 현재 미리 보기에 있으며 SLA 및 해당 서비스 수준은 이 기능의 미리 보기 상태 중 성능 또는 가용성 문제에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-473">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="66204-474">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="66204-474">Known issues</span></span>

- <span data-ttu-id="66204-475">**문제: 자동 확장된 보관 파일을 마이그레이션할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="66204-475">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="66204-476">테넌트 간 마이그레이션 기능은 특정 사용자에 대한 기본 사서함 및 보관 사서함의 마이그레이션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-476">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="66204-477">그러나 원본의 사용자에게 자동 확장 보관함이 있는 경우(즉, 두 개 이상의 보관 사서함을 의미) 이 기능은 추가 보관 파일을 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-477">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="66204-478">**문제: 소유하지 않은 smtp proxyAddress를 사용하는 클라우드 메일사용자가 MRS 이동을 차단합니다.**</span><span class="sxs-lookup"><span data-stu-id="66204-478">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="66204-479">대상 테넌트 MailUser 개체를 만들 때 모든 SMTP 프록시 주소가 대상 테넌트 조직에 속하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-479">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="66204-480">SMTP proxyAddress가 로컬 테넌트에 속하지 않은 대상 메일 사용자에 있는 경우 MailUser를 Mailbox로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-480">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="66204-481">이는 사서함 개체가 테넌트가 권한이 있는 도메인(테넌트가 클레임한 도메인)에서만 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-481">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span>

  - <span data-ttu-id="66204-482">Azure AD 커넥트 사용하여 사용자를 동기화하는 경우 사서함이 있는 원본 테넌트(laran@contoso.onmicrosoft.com)를 대상으로 하는 ExternalEmailAddress를 사용하여 사내 메일 사용자 개체를 프로비전하고 PrimarySMTPAddress를 대상 테넌트(Lara.Newton@northwind.com)에 있는 도메인으로 스탬프 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-482">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="66204-483">이러한 값은 테넌트와 동기화되어 적절한 메일 사용자가 프로비전되어 마이그레이션할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-483">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="66204-484">예제 개체는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-484">An example object is shown here.</span></span>

    ```powershell
    target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses
    ExternalEmailAddress               EmailAddresses
    --------------------               --------------
    SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com}
    ```

   > [!NOTE]
   > <span data-ttu-id="66204-485">전자 *contoso.onmicrosoft.com* 주소가  EmailAddresses/proxyAddresses 배열에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-485">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="66204-486">**문제: "외부" 기본 SMTP 주소가 있는 MailUser 개체가 수정/"내부" 회사 클레임 도메인으로 다시 설정**</span><span class="sxs-lookup"><span data-stu-id="66204-486">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

  <span data-ttu-id="66204-487">MailUser 개체는 로컬이 아닌 사서함에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="66204-487">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="66204-488">테넌트 간 사서함 마이그레이션의 경우 MailUser 개체를 사용하여 원본 사서함(대상 조직의 관점에서) 또는 대상 사서함(원본 조직의 관점에서)을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-488">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="66204-489">MailUsers에는 디렉터리에 있는 사서함 사용자의 표시된 SMTP 주소를 나타내는 실제 사서함(ProxyTest@fabrikam.onmicrosoft.com) 및 primarySMTP 주소의 smtp 주소를 나타내는 ExternalEmailAddress(targetAddress)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-489">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="66204-490">일부 조직에서는 기본 SMTP 주소를 로컬 테넌트가 소유/확인한 주소가 아닌 외부 SMTP 주소로 표시하기로 fabrikam.com(예: contoso.com.</span><span class="sxs-lookup"><span data-stu-id="66204-490">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="66204-491">그러나 라이선스 작업을 통해 Exchange 서비스 계획 개체가 MailUser에 적용되면 기본 SMTP 주소가 수정되어 로컬 조직(contoso.com)에서 확인된 도메인으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-491">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="66204-492">두 가지 이유로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-492">There are two potential reasons:</span></span>

  - <span data-ttu-id="66204-493">모든 Exchange 서비스 계획이 MailUser에 적용되면 Azure AD 프로세스에서 프록시 스크러빙을 적용하여 로컬 조직이 다른 테넌트에서 메일을 보내거나 스푸핑하거나 메일을 보낼 수 없는지 확인하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-493">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="66204-494">로컬 조직에서 주소를 확인하지 않은 경우 이러한 서비스 계획이 있는 받는 사람 개체의 SMTP 주소가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-494">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="66204-495">예에서와 같습니다. Fabikam.com 도메인은 contoso.onmicrosoft.com 확인되지 않았기 때문에 스크러빙을 통해 fabrikam.com 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-495">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="66204-496">MailUser에서 이러한 외부 도메인을 유지하려면 마이그레이션 전이나 마이그레이션 후에 마이그레이션 프로세스를 변경하여 이동이 완료된 후 또는 이동 전에 라이선스를 제거하여 사용자가 예상되는 외부 브랜더를 적용하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-496">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="66204-497">메일 서비스에 영향을 주지 않도록 사서함 개체에 적절한 사용이 허가되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-497">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="66204-498">테넌트의 MailUser에서 서비스 계획을 제거하는 Contoso.onmicrosoft.com 스크립트가 여기에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-498">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION"
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo
    ```

       <span data-ttu-id="66204-499">할당된 ServicePlans 집합의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-499">Results in the set of ServicePlans assigned are shown here.</span></span>

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

    <span data-ttu-id="66204-500">사용자의 PrimarySMTPAddress는 더 이상 스크러빙하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-500">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="66204-501">fabrikam.com 도메인은 contoso.onmicrosoft.com 소유하지 않고 디렉터리에 표시된 기본 SMTP 주소로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="66204-501">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

    <span data-ttu-id="66204-502">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-502">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress
    ------------------        -------------------------               --------------------
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com
    ```

    - <span data-ttu-id="66204-503">msExchRemoteRecipientType이 8(DeprovisionMailbox)로 설정되어 있는 경우 대상 테넌트로 마이그레이션된 사내 메일 사용자에 대해 Azure의 프록시 스크러빙 논리는 비공식 도메인을 제거하고 primarySMTP를 소유 도메인으로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66204-503">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="66204-504">프록시 스크럽 논리는 더 이상 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66204-504">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span>

      <span data-ttu-id="66204-505">다음은 서비스 계획이 포함된 가능한 서비스 계획의 전체 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="66204-505">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

      |<span data-ttu-id="66204-506">이름</span><span class="sxs-lookup"><span data-stu-id="66204-506">Name</span></span>|
      |---|
      |<span data-ttu-id="66204-507">Advanced eDiscovery Storage(500GB)</span><span class="sxs-lookup"><span data-stu-id="66204-507">Advanced eDiscovery Storage (500GB)</span></span>|
      |<span data-ttu-id="66204-508">고객 Lockbox</span><span class="sxs-lookup"><span data-stu-id="66204-508">Customer Lockbox</span></span>|
      |<span data-ttu-id="66204-509">데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="66204-509">Data Loss Prevention</span></span>|
      |<span data-ttu-id="66204-510">Exchange Enterprise CAL Services(EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="66204-510">Exchange Enterprise CAL Services (EOP, DLP)</span></span>|
      |<span data-ttu-id="66204-511">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="66204-511">Exchange Essentials</span></span>|
      |<span data-ttu-id="66204-512">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="66204-512">Exchange Foundation</span></span>|
      |<span data-ttu-id="66204-513">Exchange Online(P1)</span><span class="sxs-lookup"><span data-stu-id="66204-513">Exchange Online (P1)</span></span>|
      |<span data-ttu-id="66204-514">Exchange Online(계획 1)</span><span class="sxs-lookup"><span data-stu-id="66204-514">Exchange Online (Plan 1)</span></span>|
      |<span data-ttu-id="66204-515">Exchange Online(계획 2)</span><span class="sxs-lookup"><span data-stu-id="66204-515">Exchange Online (Plan 2)</span></span>|
      |<span data-ttu-id="66204-516">Exchange Online용 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="66204-516">Exchange Online Archiving for Exchange Online</span></span>|
      |<span data-ttu-id="66204-517">Exchange Server용 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="66204-517">Exchange Online Archiving for Exchange Server</span></span>|
      |<span data-ttu-id="66204-518">Exchange Online 비활성 사용자 추가 기능</span><span class="sxs-lookup"><span data-stu-id="66204-518">Exchange Online Inactive User Add-on</span></span>|
      |<span data-ttu-id="66204-519">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="66204-519">Exchange Online Kiosk</span></span>|
      |<span data-ttu-id="66204-520">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="66204-520">Exchange Online Multi-Geo</span></span>|
      |<span data-ttu-id="66204-521">Exchange Online 요금제 1</span><span class="sxs-lookup"><span data-stu-id="66204-521">Exchange Online Plan 1</span></span>|
      |<span data-ttu-id="66204-522">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="66204-522">Exchange Online POP</span></span>|
      |<span data-ttu-id="66204-523">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="66204-523">Exchange Online Protection</span></span>|
      |<span data-ttu-id="66204-524">정보 장벽</span><span class="sxs-lookup"><span data-stu-id="66204-524">Information Barriers</span></span>|
      |<span data-ttu-id="66204-525">Office 365 보호 - Premium</span><span class="sxs-lookup"><span data-stu-id="66204-525">Information Protection for Office 365 - Premium</span></span>|
      |<span data-ttu-id="66204-526">Office 365 보호 - 표준</span><span class="sxs-lookup"><span data-stu-id="66204-526">Information Protection for Office 365 - Standard</span></span>|
      |<span data-ttu-id="66204-527">Insights By MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="66204-527">Insights by MyAnalytics</span></span>|
      |<span data-ttu-id="66204-528">Microsoft 365 고급 감사</span><span class="sxs-lookup"><span data-stu-id="66204-528">Microsoft 365 Advanced Auditing</span></span>|
      |<span data-ttu-id="66204-529">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="66204-529">Microsoft Bookings</span></span>|
      |<span data-ttu-id="66204-530">Microsoft 비즈니스 센터</span><span class="sxs-lookup"><span data-stu-id="66204-530">Microsoft Business Center</span></span>|
      |<span data-ttu-id="66204-531">Microsoft MyAnalytics(전체)</span><span class="sxs-lookup"><span data-stu-id="66204-531">Microsoft MyAnalytics (Full)</span></span>|
      |<span data-ttu-id="66204-532">Office 365 고급 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="66204-532">Office 365 Advanced eDiscovery</span></span>|
      |<span data-ttu-id="66204-533">Microsoft Defender for Office 365(계획 1)</span><span class="sxs-lookup"><span data-stu-id="66204-533">Microsoft Defender for Office 365 (Plan 1)</span></span>|
      |<span data-ttu-id="66204-534">Microsoft Defender for Office 365(계획 2)</span><span class="sxs-lookup"><span data-stu-id="66204-534">Microsoft Defender for Office 365 (Plan 2)</span></span>|
      |<span data-ttu-id="66204-535">Office 365 권한 있는 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="66204-535">Office 365 Privileged Access Management</span></span>|
      |<span data-ttu-id="66204-536">Premium 암호화의 Office 365</span><span class="sxs-lookup"><span data-stu-id="66204-536">Premium Encryption in Office 365</span></span>|
      ||
