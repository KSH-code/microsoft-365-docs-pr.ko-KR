---
title: MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: AllowSelfServicePurchase PowerShell cmdlet을 사용하여 셀프 서비스 구매를 켜거나 끄는 방법을 학습합니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9fb5593855f9523198a3d70548e444a831e82c80
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918245"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="c6611-103">MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용</span><span class="sxs-lookup"><span data-stu-id="c6611-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="c6611-104">**이제 MSCommerce** PowerShell 모듈을 [PowerShell 갤러리에서 사용할 수 있습니다.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="c6611-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="c6611-105">이 모듈에는 조직의 사용자가 셀프 서비스 구매를 할 수 있는지 여부를 제어할 수 있는 **AllowSelfServicePurchase에** 대한 **PolicyID** 매개 변수 값이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="c6611-106">**MSCommerce** PowerShell 모듈을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="c6611-107">**AllowSelfServicePurchase** 매개 변수 값의 기본 상태(사용 또는 사용 안 하도록 설정되어 있는지 여부)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="c6611-108">해당 제품 목록 및 셀프 서비스 구매를 사용할 수 있는지 여부 보기</span><span class="sxs-lookup"><span data-stu-id="c6611-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="c6611-109">특정 제품의 현재 설정을 보거나 수정하여 특정 제품을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="c6611-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="c6611-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6611-110">Requirements</span></span>

<span data-ttu-id="c6611-111">**MSCommerce** PowerShell 모듈을 사용하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="c6611-112">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="c6611-112">A Windows 10 device</span></span>
- <span data-ttu-id="c6611-113">장치에 대한 관리자 권한</span><span class="sxs-lookup"><span data-stu-id="c6611-113">Administrator permission for the device</span></span>
- <span data-ttu-id="c6611-114">테넌트에 대한 전역 또는 청구 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="c6611-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="c6611-115">MSCommerce PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="c6611-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="c6611-116">WINDOWS 10 디바이스에 **MSCommerce** PowerShell 모듈을 한 번 설치한 다음 시작할 각 PowerShell 세션으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="c6611-117">PowerShell **갤러리에서 MSCommerce** [PowerShell 모듈을 다운로드합니다.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="c6611-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="c6611-118">**PowerShellGet을** 사용하여 **MSCommerce** PowerShell 모듈을 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="c6611-119">PowerShell 세션으로 MSCommerce 가져오기</span><span class="sxs-lookup"><span data-stu-id="c6611-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="c6611-120">Windows 10 디바이스에 모듈을 설치한 후 시작하는 각 PowerShell 세션으로 모듈을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="c6611-121">PowerShell 세션으로 가져오기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="c6611-122">자격 증명을 사용하여 MSCommerce에 연결</span><span class="sxs-lookup"><span data-stu-id="c6611-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="c6611-123">자격 증명을 사용하여 PowerShell 모듈에 연결하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="c6611-124">이 명령은 현재 PowerShell 세션을 Azure Active Directory 테넌트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="c6611-125">이 명령은 연결할 테넌트의 사용자 이름과 암호를 묻는 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="c6611-126">자격 증명에 대해 다단계 인증을 사용하도록 설정한 경우 대화형 옵션을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="c6611-127">AllowSelfServicePurchase에 대한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="c6611-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="c6611-128">조직에 따라 **AllowSelfServicePurchase** 매개 변수 값 및 기본 상태에 대한 설명을 확인하도록 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="c6611-129">셀프 서비스 구매 제품 및 상태 목록 보기</span><span class="sxs-lookup"><span data-stu-id="c6611-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="c6611-130">사용 가능한 모든 셀프 서비스 구매 제품 목록과 각 제품의 상태를 확인한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="c6611-131">다음 표에는 사용 가능한 제품과 **해당 ProductId가 나열됩니다.**</span><span class="sxs-lookup"><span data-stu-id="c6611-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="c6611-132">제품</span><span class="sxs-lookup"><span data-stu-id="c6611-132">Product</span></span> | <span data-ttu-id="c6611-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="c6611-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="c6611-134">사용자당 Power Apps</span><span class="sxs-lookup"><span data-stu-id="c6611-134">Power Apps per user</span></span> | <span data-ttu-id="c6611-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="c6611-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="c6611-136">사용자당 전원 자동화</span><span class="sxs-lookup"><span data-stu-id="c6611-136">Power Automate per user</span></span> | <span data-ttu-id="c6611-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="c6611-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="c6611-138">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="c6611-138">Power Automate RPA</span></span> | <span data-ttu-id="c6611-139">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="c6611-139">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="c6611-140">Power BI Premium(독립 실행형)</span><span class="sxs-lookup"><span data-stu-id="c6611-140">Power BI Premium (standalone)</span></span> | <span data-ttu-id="c6611-141">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="c6611-141">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="c6611-142">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="c6611-142">Power BI Pro</span></span> | <span data-ttu-id="c6611-143">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="c6611-143">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="c6611-144">프로젝트 계획 1</span><span class="sxs-lookup"><span data-stu-id="c6611-144">Project Plan 1</span></span> | <span data-ttu-id="c6611-145">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="c6611-145">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="c6611-146">프로젝트 계획 3</span><span class="sxs-lookup"><span data-stu-id="c6611-146">Project Plan 3</span></span> | <span data-ttu-id="c6611-147">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="c6611-147">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="c6611-148">Visio 요금제 1</span><span class="sxs-lookup"><span data-stu-id="c6611-148">Visio Plan 1</span></span> | <span data-ttu-id="c6611-149">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="c6611-149">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="c6611-150">Visio 요금제 2</span><span class="sxs-lookup"><span data-stu-id="c6611-150">Visio Plan 2</span></span> | <span data-ttu-id="c6611-151">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="c6611-151">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="c6611-152">AllowSelfServicePurchase의 상태 보기 또는 설정</span><span class="sxs-lookup"><span data-stu-id="c6611-152">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="c6611-153">셀프 서비스 구매에 사용할 수 있는 제품 목록을 보고 나면 특정 제품의 설정을 보거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-153">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="c6611-154">특정 제품에 대한 정책 설정을 얻었다면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-154">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="c6611-155">특정 제품에 대해 정책 설정을 사용하도록 설정하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-155">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="c6611-156">특정 제품에 대한 정책 설정을 사용하지 않도록 설정하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-156">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="c6611-157">AllowSelfServicePurchase를 사용하지 않도록 설정하는 예제 스크립트</span><span class="sxs-lookup"><span data-stu-id="c6611-157">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="c6611-158">다음 예제에서는 **MSCommerce** 모듈을 가져오고, 계정으로 로그인하고, Power Automate용 **ProductId를** 가져온 다음 해당 제품에 대해 **AllowSelfServicePurchase를** 사용하지 않도록 설정하는 방법을 설명하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-158">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="c6611-159">문제 해결</span><span class="sxs-lookup"><span data-stu-id="c6611-159">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="c6611-160">문제</span><span class="sxs-lookup"><span data-stu-id="c6611-160">Problem</span></span>

<span data-ttu-id="c6611-161">다음과 같은 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-161">You see the following error message:</span></span>

> <span data-ttu-id="c6611-162">HandleError : PolicyId 'AllowSelfServicePurchase', ErrorMessage를 사용하여 정책을 검색하지 못했습니다. - 연결이 닫혔습니다. 보내기 시 예기치 않은 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-162">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="c6611-163">이전 버전의 TLS(전송 계층 보안) 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-163">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="c6611-164">이 서비스를 연결하려면 TLS 1.2 이상을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6611-164">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="c6611-165">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c6611-165">Solution</span></span>

<span data-ttu-id="c6611-166">TLS 1.2로 업그레이드: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="c6611-166">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->