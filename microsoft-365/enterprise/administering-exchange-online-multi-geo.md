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
description: PowerShell을 사용 하 여 Microsoft 365 환경에서 Exchange Online 다중 지역 설정을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 996566d67aa8ba7ebca1406cd5d6265458637fee
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546249"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="2d266-103">Multi-Geo 환경에서 Exchange Online 사서함 관리</span><span class="sxs-lookup"><span data-stu-id="2d266-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="2d266-104">Microsoft 365 환경에서 다중 지역 속성을 보고 구성 하려면 Exchange Online PowerShell이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="2d266-105">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d266-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="2d266-106">사용자 개체의 **PreferredDataLocation** 속성을 보려면 v1.x에서 [Microsoft Azure Active Directory PowerShell 모듈](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="2d266-107">AAD Connect를 통해 AAD에 동기화된 사용자 개체의 **PreferredDataLocation** 값은 AAD PowerShell을 통해 직접 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="2d266-108">클라우드 전용 사용자 개체는 AAD PowerShell을 통해 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="2d266-109">Azure AD PowerShell에 연결하려면 [PowerShell에 연결](connect-to-microsoft-365-powershell.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d266-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="2d266-110">Exchange Online PowerShell을 사용하여 지리적 위치에 직접 연결</span><span class="sxs-lookup"><span data-stu-id="2d266-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="2d266-111">일반적으로 Exchange Online PowerShell은 중앙 지리적 위치에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="2d266-112">그러나 위성 지리적 위치에 직접 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="2d266-113">특정 위치의 사용자만 관리하는 경우 성능 개선을 위해 해당 위성 위치에 직접 연결할 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="2d266-114">EXO V2 모듈을 설치하고 사용하는 데 필요한 사항에 대한 자세한 내용은 [EXO V2 모듈 설치 및 유지 관리](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d266-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="2d266-115">Exchange Online PowerShell을 특정 지리적 위치에 연결 하려면 *Connectionuri* 매개 변수가 일반 연결 지침과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="2d266-116">나머지 명령과 값은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="2d266-117">특히 `?email=<emailaddress>` _connectionuri_ 값의 끝에 값을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="2d266-118">`<emailaddress>` 는 대상 지리적 위치에 있는 **모든** 사서함의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="2d266-119">해당 사서함에 대 한 사용 권한 또는 자격 증명과의 관계는 요인이 아닙니다. 전자 메일 주소는 Exchange Online PowerShell에 연결 하는 것을 간단 하 게 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="2d266-120">Microsoft 365 또는 Microsoft 365 GCC 고객은 일반적으로 _Connectionuri_ 매개 변수를 사용 하 여 Exchange Online PowerShell에 연결할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="2d266-121">그러나 특정 지리적 위치에 연결 하려면 값에 _Connectionuri_ 매개 변수를 사용 해야 `?email=<emailaddress>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a><span data-ttu-id="2d266-122">MFA (multi-factor authentication)를 사용 하 여 Exchange Online PowerShell에서 지리적 위치에 연결</span><span class="sxs-lookup"><span data-stu-id="2d266-122">Connect to a geo location in Exchange Online PowerShell using multi-factor authentication (MFA)</span></span>

1. <span data-ttu-id="2d266-123">Windows PowerShell 창에서 다음 명령을 실행하여 EXO V2 모듈을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-123">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="2d266-124">다음 예제에서는 admin@contoso.onmicrosoft.com이 관리자 계정이 고, 대상 지리적 위치는 사서함 olga@contoso.onmicrosoft.com가 상주 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-124">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a><span data-ttu-id="2d266-125">MFA를 사용 하지 않고 Exchange Online PowerShell에서 지리적 위치에 연결</span><span class="sxs-lookup"><span data-stu-id="2d266-125">Connect to a geo location in Exchange Online PowerShell without using MFA</span></span>

1. <span data-ttu-id="2d266-126">Windows PowerShell 창에서 다음 명령을 실행하여 EXO V2 모듈을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="2d266-127">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-127">Run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="2d266-128">표시되는 **Windows PowerShell 자격 증명 요청** 대화 상자에서 회사 또는 학교 계정 사용자 이름과 비밀번호를 입력한 다음, **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-128">In the **Windows PowerShell Credential Request** dialog box that appears, type your work or school account and password, and then click **OK**.</span></span>

3. <span data-ttu-id="2d266-129">다음 예제에서는 사서함 olga@contoso.onmicrosoft.com가 상주 하는 위치에서 대상 지리적 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-129">In the following example, the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="2d266-130">Exchange Online 조직에서 구성된 사용 가능한 지리적 위치 보기</span><span class="sxs-lookup"><span data-stu-id="2d266-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="2d266-131">Microsoft 365 Multi-Geo에서 구성된 지리적 위치 목록을 보려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="2d266-132">Exchange Online 조직의 중앙 지리적 위치 보기</span><span class="sxs-lookup"><span data-stu-id="2d266-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="2d266-133">테넌트의 중앙 지리적 위치를 보려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="2d266-134">사서함의 지리적 위치 찾기</span><span class="sxs-lookup"><span data-stu-id="2d266-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="2d266-135">Exchange Online PowerShell의 **Get-Mailbox** cmdlet은 사서함에 다음과 같은 Multi-Geo 관련 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="2d266-136">**Database**: 데이터베이스 이름의 첫 세 글자는 지역 코드에 해당하며, 사서함의 현재 위치를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="2d266-137">온라인 보관 사서함의 경우 **ArchiveDatabase** 속성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="2d266-138">**MailboxRegion**: 관리자가 설정한 지리적 위치 코드를 지정합니다(Azure AD의 **PreferredDataLocation**에서 동기화됨).</span><span class="sxs-lookup"><span data-stu-id="2d266-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="2d266-139">**MailboxRegionLastUpdateTime**: MailboxRegion이 마지막으로 업데이트(자동 또는 수동으로)된 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="2d266-140">사서함의 속성을 보려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="2d266-141">예를 들어 chris@contoso.onmicrosoft.com의 사서함 위치 정보를 보려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="2d266-142">이 명령의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="2d266-143">데이터베이스 이름에 있는 지리적 위치 코드가 **MailboxRegion** 값과 일치 하지 않으면 사서함이 자동으로 재배치 큐에 배치 되 고 **MailboxRegion** 값으로 지정 된 지리적 위치로 이동 됩니다 (이러한 속성 값 간에 불일치를 검색 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2d266-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="2d266-144">기존 클라우드 전용 사서함을 특정 지리적 위치로 이동</span><span class="sxs-lookup"><span data-stu-id="2d266-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="2d266-145">클라우드 전용 사용자는 AAD Connect로 테넌트에 동기화되지 않은 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="2d266-146">이 사용자는 Azure AD에서 직접 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="2d266-147">Windows PowerShell용 Azure AD 모듈에서 **Get-MsolUser** 및 **Set-MsolUser** cmdlet을 사용하여 클라우드 전용 사용자의 사서함을 저장할 지리적 위치를 보거나 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="2d266-148">사용자의 **PreferredDataLocation** 값을 보려면 Azure AD PowerShell에서 이 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="2d266-149">예를 들어 사용자 michelle@contoso.onmicrosoft.com의 **PreferredDataLocation** 값을 보려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="2d266-150">클라우드 전용 사용자 개체의 **PreferredDataLocation** 값을 수정하려면 Azure AD PowerShell에서 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="2d266-151">예를 들어 사용자 michelle@contoso.onmicrosoft.com의 유럽 연합(EUR) 지역에 **PreferredDataLocation** 값을 설정하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="2d266-152">앞에서 설명한 것 처럼, 온-프레미스 Active Directory에서 동기화 된 사용자 개체에는이 절차를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="2d266-153">Active Directory에서 **PreferredDataLocation** 값을 변경하고 AAD Connect를 사용하여 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="2d266-154">자세한 내용은 [Azure Active Directory Connect 동기화: Microsoft 365 리소스의 기본 데이터 위치 구성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d266-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="2d266-155">새로운 지리적 위치로 사서함 위치를 변경하는 데 걸리는 시간은 몇 가지 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="2d266-156">사서함 크기 및 유형</span><span class="sxs-lookup"><span data-stu-id="2d266-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="2d266-157">이동 중인 사서함 수</span><span class="sxs-lookup"><span data-stu-id="2d266-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="2d266-158">이동 리소스의 가용성</span><span class="sxs-lookup"><span data-stu-id="2d266-158">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="2d266-159">사용하지 않도록 설정한 소송 보존 중인 사서함 이동</span><span class="sxs-lookup"><span data-stu-id="2d266-159">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="2d266-160">eDiscovery 목적으로 보존된 소송 보존 중인 사서함을 사용하지 않도록 설정하면, 사용하지 않도록 설정한 상태에서 **PreferredDataLocation** 값을 변경해도 이동할 수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-160">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="2d266-161">사용하지 않도록 설정한 소송 보존 중인 사서함을 이동하려면:</span><span class="sxs-lookup"><span data-stu-id="2d266-161">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="2d266-162">사서함에 일시적으로 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-162">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="2d266-163">**PreferredDataLocation**을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-163">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="2d266-164">선택한 지리적 위치로 라이선스를 이동한 후 사서함에서 라이선스를 제거함으로써 사용 안 함 상태로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-164">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="2d266-165">특정 지리적 위치에 새 클라우드 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="2d266-165">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="2d266-166">특정 지리적 위치에 새 사서함을 만들려면 다음 단계 중 하나를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-166">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="2d266-167">Exchange Online에 사서함을 만들기 *전에* 이전 섹션에 설명된 대로 **PreferredDataLocation** 값부터 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-167">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="2d266-168">예를 들어 라이선스를 할당하기 전에 먼저 사용자의 **PreferredDataLocation** 값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-168">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="2d266-169">**PreferredDataLocation** 값을 설정함과 동시에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-169">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="2d266-170">특정 지리적 위치에 새로운 클라우드 전용 라이선스 사용자 (AAD Connect 동기화가 아닌)를 만들려면 Azure AD PowerShell에서 다음 구문을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d266-170">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="2d266-171">이 예제에서는 다음 값을 사용하여 Elizabeth Brunner를 위한 새 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-171">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="2d266-172">사용자 계정 이름: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2d266-172">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="2d266-173">이름: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="2d266-173">First name: Elizabeth</span></span>
- <span data-ttu-id="2d266-174">성: Brunner</span><span class="sxs-lookup"><span data-stu-id="2d266-174">Last name: Brunner</span></span>
- <span data-ttu-id="2d266-175">표시할 이름: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="2d266-175">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="2d266-176">비밀번호: 임의로 생성되고 명령의 결과에 표시됨(*비밀번호* 매개 변수를 사용하지 않고 있기 때문)</span><span class="sxs-lookup"><span data-stu-id="2d266-176">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="2d266-177">라이선스: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="2d266-177">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="2d266-178">위치: 오스트레일리아(AUS)</span><span class="sxs-lookup"><span data-stu-id="2d266-178">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="2d266-179">새 사용자 계정을 만들고 Azure AD PowerShell에서 LicenseAssignment 값을 찾는 방법에 대한 자세한 내용은 [PowerShell을 사용하여 사용자 계정 만들기](create-user-accounts-with-microsoft-365-powershell.md) 및 [PowerShell을 사용하여 라이선스 및 서비스 보기](view-licenses-and-services-with-microsoft-365-powershell.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d266-179">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2d266-180">Exchange Online PowerShell로 사서함을 사용하도록 설정하고 해당 사서함을 **PreferredDataLocation**에 지정된 지리적 위치에 직접 만들려면 **Enable-Mailbox** 또는 **New-Mailbox** 등의 Exchange Online cmdlet을 클라우드 서비스에 직접 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-180">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="2d266-181">온 - 프레미스 Exchange PowerShell에서 **Enable-RemoteMailbox** cmdlet를 사용하면 사서함이 중앙 지리적 위치에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-181">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="2d266-182">특정 지리적 위치에 기존 온-프레미스 사서함 등록</span><span class="sxs-lookup"><span data-stu-id="2d266-182">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="2d266-183">표준 등록 도구와 프로세스를 사용하여 사서함을 온-프레미스 Exchange 조직에서 Exchange Online으로 마이그레이션할 수 있습니다([EAC의 마이그레이션 대시보드](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), Exchange Online PowerShell의 [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet 포함).</span><span class="sxs-lookup"><span data-stu-id="2d266-183">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="2d266-184">첫 번째 단계는 등록될 사서함마다 사용자 개체가 있는지 확인하고 Azure AD에 올바른 **PreferredDataLocation** 값이 구성되었는지 확인하는 일입니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-184">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="2d266-185">등록 도구는 **PreferredDataLocation** 값을 고려하고 사서함을 지정된 지리적 위치에 직접 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-185">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="2d266-186">또는 Exchange Online PowerShell의 [새로 만들기 MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet을 사용하는 다음 단계를 통해 사서함을 특정 지리적 위치에 직접 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-186">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="2d266-187">등록될 사서함마다 사용자 개체가 있고 **PreferredDataLocation**이 Azure AD에서 원하는 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-187">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="2d266-188">**PreferredDataLocation** 값은 Exchange Online에서 해당 메일 사용자 개체의 **MailboxRegion** 특성에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-188">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="2d266-189">이 항목 앞부분의 연결 지침을 사용하여 특정 위성 지리적 위치에 직접 연결하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d266-189">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="2d266-190">Exchange Online PowerShell에서 다음 명령을 실행하여, 변수에서 사서함 마이그레이션을 수행하는 데 사용되는 온-프레미스 관리자 자격 증명을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-190">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="2d266-191">Exchange Online PowerShell에서 다음 예제와 비슷한 새로운 **New-MoveRequest**를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-191">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="2d266-192">온-프레미스 Exchange에서 현재 연결된 위성 지리적 위치로 마이그레이션해야 할 모든 사서함에 4단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-192">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="2d266-193">다른 위성 지리적 위치에 추가 사서함을 마이그레이션해야 할 경우 각각의 특정 위치에 2단계에서 4단계까지를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-193">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="2d266-194">Multi-Geo 보고</span><span class="sxs-lookup"><span data-stu-id="2d266-194">Multi-geo reporting</span></span>

<span data-ttu-id="2d266-195">Microsoft 365 관리자 센터의 **Multi-Geo 사용 보고서**는 지리적 위치별 사용자 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-195">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="2d266-196">보고서는 이번 달의 사용자 분포를 표시하고 지난 6개월 동안의 기록 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d266-196">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d266-197">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d266-197">See also</span></span>

[<span data-ttu-id="2d266-198">Windows PowerShell로 Microsoft 365 및 Exchange Online 관리</span><span class="sxs-lookup"><span data-stu-id="2d266-198">Managing Microsoft 365 and Exchange Online with Windows PowerShell</span></span>](https://support.office.com//article/06a743bb-ceb6-49a9-a61d-db4ffdf54fa6)
