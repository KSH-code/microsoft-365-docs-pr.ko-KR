---
title: Multi-Geo 환경에서 Exchange Online 사서함 관리
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: PowerShell을 사용하여 Microsoft 365 환경에서 Exchange Online Multi-Geo 설정을 관리하는 방법을 확인합니다.
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552010"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="1a3bd-103">Multi-Geo 환경에서 Exchange Online 사서함 관리</span><span class="sxs-lookup"><span data-stu-id="1a3bd-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="1a3bd-104">Microsoft 365 환경에서 다중 지리적 속성을 보고 구성하려면 Exchange Online PowerShell이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="1a3bd-105">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="1a3bd-106">사용자 개체의 **PreferredDataLocation** 속성을 보려면 v1.x에서 [Microsoft Azure Active Directory PowerShell 모듈](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="1a3bd-107">AAD Connect를 통해 AAD에 동기화된 사용자 개체의 **PreferredDataLocation** 값은 AAD PowerShell을 통해 직접 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="1a3bd-108">클라우드 전용 사용자 개체는 AAD PowerShell을 통해 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="1a3bd-109">Azure AD PowerShell에 연결하려면 [PowerShell에 연결](connect-to-microsoft-365-powershell.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="1a3bd-110">Exchange Online PowerShell을 사용하여 지리적 위치에 직접 연결</span><span class="sxs-lookup"><span data-stu-id="1a3bd-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="1a3bd-111">일반적으로 Exchange Online PowerShell은 중앙 지리적 위치에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="1a3bd-112">그러나 위성 지리적 위치에 직접 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="1a3bd-113">특정 위치의 사용자만 관리하는 경우 성능 개선을 위해 해당 위성 위치에 직접 연결할 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="1a3bd-114">EXO V2 모듈을 설치하고 사용하는 데 필요한 사항에 대한 자세한 내용은 [EXO V2 모듈 설치 및 유지 관리](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="1a3bd-115">Exchange Online PowerShell을 특정 지리적 위치에 연결하기 위해 *ConnectionUri* 매개 변수는 일반 연결 지침과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="1a3bd-116">나머지 명령과 값은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="1a3bd-117">특히 ConnectionUri 값의 `?email=<emailaddress>` 끝에 값을 _추가해야_ 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="1a3bd-118">`<emailaddress>` 는 대상 지리적 위치에 있는 **모든** 사서함의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="1a3bd-119">해당 사서함에 대한 사용 권한 또는 자격 증명과의 관계는 요인이 되지 않습니다. 전자 메일 주소는 간단히 Exchange Online PowerShell에 연결할 위치를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="1a3bd-120">Microsoft 365 또는 Microsoft 365 GCC 고객은 일반적으로 _ConnectionUri_ 매개 변수를 사용하여 Exchange Online PowerShell에 연결할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="1a3bd-121">그러나 특정 지리적 위치에 연결하려면 _값에서_ 사용할 수 있도록 ConnectionUri 매개 변수를 `?email=<emailaddress>` 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="1a3bd-122">Exchange Online PowerShell에서 지리적 위치에 연결</span><span class="sxs-lookup"><span data-stu-id="1a3bd-122">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="1a3bd-123">다음 연결 지침은 MFA(다단계 인증)에 대해 구성되거나 구성되지 않은 계정에 대해 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-123">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="1a3bd-124">Windows PowerShell 창에서 다음 명령을 실행하여 EXO V2 모듈을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-124">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="1a3bd-125">다음 예에서 admin@contoso.onmicrosoft.com 계정은 관리자 계정이고 대상 지리적 위치는 사서함 계정이 olga@contoso.onmicrosoft.com 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-125">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="1a3bd-126">메시지에 admin@contoso.onmicrosoft.com 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-126">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="1a3bd-127">계정이 MFA에 대해 구성된 경우 보안 코드도 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-127">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="1a3bd-128">Exchange Online 조직에서 구성된 사용 가능한 지리적 위치 보기</span><span class="sxs-lookup"><span data-stu-id="1a3bd-128">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="1a3bd-129">Microsoft 365 Multi-Geo에서 구성된 지리적 위치 목록을 보려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-129">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="1a3bd-130">Exchange Online 조직의 중앙 지리적 위치 보기</span><span class="sxs-lookup"><span data-stu-id="1a3bd-130">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="1a3bd-131">테넌트의 중앙 지리적 위치를 보려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-131">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="1a3bd-132">사서함의 지리적 위치 찾기</span><span class="sxs-lookup"><span data-stu-id="1a3bd-132">Find the geo location of a mailbox</span></span>

<span data-ttu-id="1a3bd-133">Exchange Online PowerShell의 **Get-Mailbox** cmdlet은 사서함에 다음과 같은 Multi-Geo 관련 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-133">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="1a3bd-134">**Database**: 데이터베이스 이름의 첫 세 글자는 지역 코드에 해당하며, 사서함의 현재 위치를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-134">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="1a3bd-135">온라인 보관 사서함의 경우 **ArchiveDatabase** 속성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-135">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="1a3bd-136">**MailboxRegion**: 관리자가 설정한 지리적 위치 코드를 지정합니다(Azure AD의 **PreferredDataLocation** 에서 동기화됨).</span><span class="sxs-lookup"><span data-stu-id="1a3bd-136">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="1a3bd-137">**MailboxRegionLastUpdateTime**: MailboxRegion이 마지막으로 업데이트(자동 또는 수동으로)된 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-137">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="1a3bd-138">사서함의 속성을 보려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-138">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="1a3bd-139">예를 들어 chris@contoso.onmicrosoft.com의 사서함 위치 정보를 보려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-139">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="1a3bd-140">이 명령의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-140">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="1a3bd-141">데이터베이스 이름의 지리적 위치 코드가 **MailboxRegion** 값과 일치하지 않으면 사서함이 자동으로 재배치 큐에 추가되고 **MailboxRegion** 값으로 지정된 지리적 위치로 이동됩니다(Exchange Online은 이러한 속성 값 간의 불일치 검색).</span><span class="sxs-lookup"><span data-stu-id="1a3bd-141">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="1a3bd-142">기존 클라우드 전용 사서함을 특정 지리적 위치로 이동</span><span class="sxs-lookup"><span data-stu-id="1a3bd-142">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="1a3bd-143">클라우드 전용 사용자는 AAD Connect로 테넌트에 동기화되지 않은 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-143">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="1a3bd-144">이 사용자는 Azure AD에서 직접 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-144">This user was created directly in Azure AD.</span></span> <span data-ttu-id="1a3bd-145">Windows PowerShell용 Azure AD 모듈에서 **Get-MsolUser** 및 **Set-MsolUser** cmdlet을 사용하여 클라우드 전용 사용자의 사서함을 저장할 지리적 위치를 보거나 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-145">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="1a3bd-146">사용자의 **PreferredDataLocation** 값을 보려면 Azure AD PowerShell에서 이 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-146">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="1a3bd-147">예를 들어 사용자 michelle@contoso.onmicrosoft.com의 **PreferredDataLocation** 값을 보려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-147">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="1a3bd-148">클라우드 전용 사용자 개체의 **PreferredDataLocation** 값을 수정하려면 Azure AD PowerShell에서 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-148">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="1a3bd-149">예를 들어 사용자 michelle@contoso.onmicrosoft.com의 유럽 연합(EUR) 지역에 **PreferredDataLocation** 값을 설정하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-149">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="1a3bd-150">앞서 설명한 것 처럼 이 절차는 모든 사용자 개체에 대한 동기화된 사용자 개체에 대해 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-150">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="1a3bd-151">Active Directory에서 **PreferredDataLocation** 값을 변경하고 AAD Connect를 사용하여 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-151">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="1a3bd-152">자세한 내용은 [Azure Active Directory Connect 동기화: Microsoft 365 리소스의 기본 데이터 위치 구성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-152">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="1a3bd-153">새로운 지리적 위치로 사서함 위치를 변경하는 데 걸리는 시간은 몇 가지 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-153">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="1a3bd-154">사서함 크기 및 유형</span><span class="sxs-lookup"><span data-stu-id="1a3bd-154">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="1a3bd-155">이동 중인 사서함 수</span><span class="sxs-lookup"><span data-stu-id="1a3bd-155">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="1a3bd-156">이동 리소스의 가용성</span><span class="sxs-lookup"><span data-stu-id="1a3bd-156">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="1a3bd-157">비활성 사서함을 특정 지역으로 이동</span><span class="sxs-lookup"><span data-stu-id="1a3bd-157">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="1a3bd-158">**PreferredDataLocation** 값을 변경하여 준수 목적으로 보존된 비활성 사서함(예: 소송 보존 사서함)을 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-158">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="1a3bd-159">비활성 사서함을 다른 지역으로 이동하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-159">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="1a3bd-160">비활성 사서함을 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-160">Recover the inactive mailbox.</span></span> <span data-ttu-id="1a3bd-161">자세한 내용은 비활성 [사서함 복구를 참조하십시오.](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="1a3bd-161">For instructions, see [Recover an inactive mailbox](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span></span>

2. <span data-ttu-id="1a3bd-162">사서함의 이름, 별칭, 계정 또는 전자 메일 주소로 바꾸고 \<MailboxIdentity\> [Exchange Online PowerShell에서](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)다음 명령을 실행하여 관리되는 폴더 도우미가 복구된 사서함을 처리하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-162">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="1a3bd-163">복구된 **사서함에 Exchange Online 계획 2** 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-163">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="1a3bd-164">이 단계는 사서함을 다시 소송 보류에 두는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-164">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="1a3bd-165">자세한 내용은 [사용자에게 라이선스 할당을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="1a3bd-165">For instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

4. <span data-ttu-id="1a3bd-166">이전 섹션에 설명된 바와 같이 사서함에 **PreferredDataLocation** 값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-166">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="1a3bd-167">사서함이 새 지리적 위치로 이동했다는 사실이 확인되면 복구된 사서함을 다시 소송 보류에 옮기면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-167">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="1a3bd-168">자세한 내용은 [사서함에 소송 유지를 하세요.](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)</span><span class="sxs-lookup"><span data-stu-id="1a3bd-168">For instructions, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="1a3bd-169">소송 보류가 설정되고 있는지 확인한 후 관리되는 폴더 도우미가 사서함의 이름, 별칭, 계정 또는 전자 메일 주소로 바꾸고 \<MailboxIdentity\> [Exchange Online PowerShell에서](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)다음 명령을 실행하여 사서함을 다시 처리하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-169">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="1a3bd-170">사서함과 연결된 사용자 계정을 제거하여 사서함을 다시 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-170">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="1a3bd-171">자세한 내용은 [조직에서 사용자 삭제를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="1a3bd-171">For instructions, see [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span></span> <span data-ttu-id="1a3bd-172">이 단계에서는 다른 용도의 Exchange Online 계획 2 라이선스도 릴리스합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-172">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="1a3bd-173">**참고:** 비활성 사서함을 다른 지리적 위치로 이동하면 콘텐츠 검색 결과 또는 이전 지리적 위치에서 사서함을 검색하는 능력에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-173">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="1a3bd-174">자세한 내용은 Multi-Geo 환경에서 콘텐츠 검색 [및 내보내기 기능을 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)</span><span class="sxs-lookup"><span data-stu-id="1a3bd-174">For more information, see [Searching and exporting content in Multi-Geo environments](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="1a3bd-175">특정 지리적 위치에 새 클라우드 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="1a3bd-175">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="1a3bd-176">특정 지리적 위치에 새 사서함을 만들려면 다음 단계 중 하나를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-176">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="1a3bd-177">Exchange Online에서 사서함을 만들기 전에 이전의 [](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) 기존 클라우드 전용 사서함을 특정 지리적  위치 섹션으로 이동에 설명된 바와 같이 **PreferredDataLocation** 값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-177">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="1a3bd-178">예를 들어 라이선스를 할당하기 전에 사용자에 **대해 PreferredDataLocation** 값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-178">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="1a3bd-179">**PreferredDataLocation** 값을 설정함과 동시에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-179">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="1a3bd-180">특정 지리적 위치에 새로운 클라우드 전용 라이선스 사용자 (AAD Connect 동기화가 아닌)를 만들려면 Azure AD PowerShell에서 다음 구문을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-180">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="1a3bd-181">이 예제에서는 다음 값을 사용하여 Elizabeth Brunner를 위한 새 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-181">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="1a3bd-182">사용자 계정 이름: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="1a3bd-182">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="1a3bd-183">이름: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="1a3bd-183">First name: Elizabeth</span></span>
- <span data-ttu-id="1a3bd-184">성: Brunner</span><span class="sxs-lookup"><span data-stu-id="1a3bd-184">Last name: Brunner</span></span>
- <span data-ttu-id="1a3bd-185">표시할 이름: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="1a3bd-185">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="1a3bd-186">비밀번호: 임의로 생성되고 명령의 결과에 표시됨(*비밀번호* 매개 변수를 사용하지 않고 있기 때문)</span><span class="sxs-lookup"><span data-stu-id="1a3bd-186">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="1a3bd-187">라이선스: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="1a3bd-187">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="1a3bd-188">위치: 오스트레일리아(AUS)</span><span class="sxs-lookup"><span data-stu-id="1a3bd-188">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="1a3bd-189">새 사용자 계정을 만들고 Azure AD PowerShell에서 LicenseAssignment 값을 찾는 방법에 대한 자세한 내용은 [PowerShell을 사용하여 사용자 계정 만들기](create-user-accounts-with-microsoft-365-powershell.md) 및 [PowerShell을 사용하여 라이선스 및 서비스 보기](view-licenses-and-services-with-microsoft-365-powershell.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-189">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1a3bd-190">Exchange Online PowerShell로 사서함을 사용하도록 설정하고 해당 사서함을 **PreferredDataLocation** 에 지정된 지리적 위치에 직접 만들려면 **Enable-Mailbox** 또는 **New-Mailbox** 등의 Exchange Online cmdlet을 클라우드 서비스에 직접 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-190">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="1a3bd-191">온 - 프레미스 Exchange PowerShell에서 **Enable-RemoteMailbox** cmdlet를 사용하면 사서함이 중앙 지리적 위치에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-191">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="1a3bd-192">특정 지리적 위치에 기존 온-프레미스 사서함 등록</span><span class="sxs-lookup"><span data-stu-id="1a3bd-192">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="1a3bd-193">표준 등록 도구와 프로세스를 사용하여 사서함을 온-프레미스 Exchange 조직에서 Exchange Online으로 마이그레이션할 수 있습니다([EAC의 마이그레이션 대시보드](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), Exchange Online PowerShell의 [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet 포함).</span><span class="sxs-lookup"><span data-stu-id="1a3bd-193">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="1a3bd-194">첫 번째 단계는 등록될 사서함마다 사용자 개체가 있는지 확인하고 Azure AD에 올바른 **PreferredDataLocation** 값이 구성되었는지 확인하는 일입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-194">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="1a3bd-195">등록 도구는 **PreferredDataLocation** 값을 고려하고 사서함을 지정된 지리적 위치에 직접 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-195">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="1a3bd-196">또는 Exchange Online PowerShell의 [새로 만들기 MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet을 사용하는 다음 단계를 통해 사서함을 특정 지리적 위치에 직접 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-196">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="1a3bd-197">등록될 사서함마다 사용자 개체가 있고 **PreferredDataLocation** 이 Azure AD에서 원하는 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-197">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="1a3bd-198">**PreferredDataLocation** 값은 Exchange Online에서 해당 메일 사용자 개체의 **MailboxRegion** 특성에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-198">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="1a3bd-199">이 항목 앞부분의 연결 지침을 사용하여 특정 위성 지리적 위치에 직접 연결하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-199">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="1a3bd-200">Exchange Online PowerShell에서 다음 명령을 실행하여, 변수에서 사서함 마이그레이션을 수행하는 데 사용되는 온-프레미스 관리자 자격 증명을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-200">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="1a3bd-201">Exchange Online PowerShell에서 다음 예제와 비슷한 새로운 **New-MoveRequest** 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-201">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="1a3bd-202">온-프레미스 Exchange에서 현재 연결된 위성 지리적 위치로 마이그레이션해야 할 모든 사서함에 4단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-202">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="1a3bd-203">다른 위성 지리적 위치에 추가 사서함을 마이그레이션해야 할 경우 각각의 특정 위치에 2단계에서 4단계까지를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-203">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="1a3bd-204">Multi-Geo 보고</span><span class="sxs-lookup"><span data-stu-id="1a3bd-204">Multi-geo reporting</span></span>

<span data-ttu-id="1a3bd-205">Microsoft 365 관리자 센터의 **Multi-Geo 사용 보고서** 는 지리적 위치별 사용자 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-205">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="1a3bd-206">보고서는 이번 달의 사용자 분포를 표시하고 지난 6개월 동안의 기록 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3bd-206">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a3bd-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a3bd-207">See also</span></span>

[<span data-ttu-id="1a3bd-208">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="1a3bd-208">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
