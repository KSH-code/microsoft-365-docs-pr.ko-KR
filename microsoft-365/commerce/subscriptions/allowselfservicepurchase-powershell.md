---
title: MSCommerce PowerShell 모듈에 대해 AllowSelfServicePurchase 사용
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: AllowSelfServicePurchase PowerShell cmdlet을 사용 하 여 셀프 서비스 구매를 설정 하거나 해제 하는 방법을 알아봅니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ec5ebe814066916de5cafc176cdcd82bfd416a57
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403693"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="f4071-103">MSCommerce PowerShell 모듈에 대해 AllowSelfServicePurchase 사용</span><span class="sxs-lookup"><span data-stu-id="f4071-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="f4071-104">이제 [Powershell 갤러리](https://aka.ms/allowselfservicepurchase-powershell-gallery)에서 **MSCommerce** powershell 모듈을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="f4071-105">이 모듈에는 조직의 사용자가 셀프 서비스 구매를 수행할 수 있는지 여부를 제어 하는 **AllowSelfServicePurchase** 에 대 한 **policyid** 매개 변수 값이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="f4071-106">**MSCommerce** PowerShell 모듈을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="f4071-107">사용 하거나 사용 하지 않도록 설정 되었는지 여부에 관계 없이 **AllowSelfServicePurchase** 매개 변수 값의 기본 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="f4071-108">해당 하는 제품 목록 및 셀프 서비스 구매가 사용 하도록 설정 되었는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="f4071-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="f4071-109">특정 제품에 대 한 현재 설정을 보거나 수정 하 여 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f4071-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="f4071-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4071-110">Requirements</span></span>

<span data-ttu-id="f4071-111">**MSCommerce** PowerShell 모듈을 사용 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="f4071-112">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="f4071-112">A Windows 10 device</span></span>
- <span data-ttu-id="f4071-113">장치에 대 한 관리자 권한</span><span class="sxs-lookup"><span data-stu-id="f4071-113">Administrator permission for the device</span></span>
- <span data-ttu-id="f4071-114">테 넌 트에 대 한 전역 또는 대금 청구 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="f4071-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="f4071-115">MSCommerce PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="f4071-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="f4071-116">Windows 10 장치에 **MSCommerce** PowerShell 모듈을 한 번 설치 하 고 시작한 각 powershell 세션으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="f4071-117">[Powershell 갤러리](https://aka.ms/allowselfservicepurchase-powershell-gallery)에서 **MSCommerce** PowerShell 모듈을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="f4071-118">**PowerShellGet**을 사용 하 여 **MSCommerce** PowerShell 모듈을 설치 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="f4071-119">PowerShell 세션으로 MSCommerce 가져오기</span><span class="sxs-lookup"><span data-stu-id="f4071-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="f4071-120">Windows 10 장치에 모듈을 설치한 후에는이를 시작 하는 각 PowerShell 세션으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="f4071-121">이를 PowerShell 세션으로 가져오려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="f4071-122">자격 증명을 사용 하 여 MSCommerce에 연결</span><span class="sxs-lookup"><span data-stu-id="f4071-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="f4071-123">자격 증명을 사용 하 여 PowerShell 모듈에 연결 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="f4071-124">이 명령은 현재 PowerShell 세션을 Azure Active Directory 테 넌 트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="f4071-125">이 명령은 연결 하려는 테 넌 트의 사용자 이름과 암호를 입력 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="f4071-126">자격 증명에 multi-factor authentication을 사용 하도록 설정 된 경우 대화형 옵션을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="f4071-127">AllowSelfServicePurchase에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="f4071-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="f4071-128">조직에 따라 **AllowSelfServicePurchase** 매개 변수 값 및 기본 상태에 대 한 설명을 보려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="f4071-129">셀프 서비스 구매 제품 및 해당 상태 목록 보기</span><span class="sxs-lookup"><span data-stu-id="f4071-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="f4071-130">사용 가능한 모든 셀프 서비스 구매 제품의 목록과 각 상태를 보려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="f4071-131">다음 표에는 사용 가능한 제품 및 해당 **ProductId**가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="f4071-132">제품</span><span class="sxs-lookup"><span data-stu-id="f4071-132">Product</span></span> | <span data-ttu-id="f4071-133">제품</span><span class="sxs-lookup"><span data-stu-id="f4071-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="f4071-134">사용자 당 전원 앱</span><span class="sxs-lookup"><span data-stu-id="f4071-134">Power Apps per user</span></span> | <span data-ttu-id="f4071-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="f4071-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="f4071-136">사용자 당 전원 자동화</span><span class="sxs-lookup"><span data-stu-id="f4071-136">Power Automate per user</span></span> | <span data-ttu-id="f4071-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="f4071-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="f4071-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="f4071-138">Power BI Pro</span></span> | <span data-ttu-id="f4071-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="f4071-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="f4071-140">AllowSelfServicePurchase의 상태를 보거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="f4071-141">셀프 서비스 구매에 사용할 수 있는 제품 목록을 확인 한 후에는 특정 제품에 대 한 설정을 보거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="f4071-142">특정 제품에 대 한 정책 설정을 가져오려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="f4071-143">특정 제품에 대 한 정책 설정을 사용 하도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="f4071-144">특정 제품에 대 한 정책 설정을 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="f4071-145">AllowSelfServicePurchase을 사용 하지 않도록 설정 하는 스크립트 예제</span><span class="sxs-lookup"><span data-stu-id="f4071-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="f4071-146">다음은 **MSCommerce** 모듈을 가져오고, 계정으로 로그인 하 고, 전원 자동화를 위해 제품 **일련번호** 를 가져온 후 해당 제품에 대해 **AllowSelfServicePurchase** 를 사용 하지 않도록 설정 하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="f4071-147">문제 해결</span><span class="sxs-lookup"><span data-stu-id="f4071-147">Troubleshooting</span></span>

<span data-ttu-id="f4071-148">**데**</span><span class="sxs-lookup"><span data-stu-id="f4071-148">**Problem**</span></span>

<span data-ttu-id="f4071-149">다음과 같은 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-149">You see the following error message:</span></span>

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

<span data-ttu-id="f4071-150">이전 버전의 TLS (전송 계층 보안)로 인 한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-150">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="f4071-151">이 서비스에 연결 하려면 TLS 1.2 이상을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4071-151">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="f4071-152">**해결 방법**</span><span class="sxs-lookup"><span data-stu-id="f4071-152">**Solution**</span></span>

<span data-ttu-id="f4071-153">TLS 1.2으로 업그레이드 합니다.[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="f4071-153">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
