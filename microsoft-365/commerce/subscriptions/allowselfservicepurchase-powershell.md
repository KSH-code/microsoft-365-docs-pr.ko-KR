---
title: MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: ''
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: AllowSelfServicePurchase PowerShell cmdlet을 사용하여 셀프 서비스 구매를 켜거나 끄는 방법을 학습합니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 07/16/2021
ms.openlocfilehash: 31ef425bf82f40d9720eec0a65b3278e63186ba9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172578"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>MSCommerce PowerShell 모듈에 AllowSelfServicePurchase 사용

**이제 MSCommerce** PowerShell 모듈을 [PowerShell 갤러리에서 사용할 수 있습니다.](https://aka.ms/allowselfservicepurchase-powershell-gallery) 이 모듈에는 조직의 사용자가 셀프 서비스 구매를 할 수 있는지 여부를 제어할 수 있는 **AllowSelfServicePurchase에** 대한 **PolicyID** 매개 변수 값이 포함되어 있습니다.

**MSCommerce** PowerShell 모듈을 사용하여 다음을 할 수 있습니다.

- **AllowSelfServicePurchase** 매개 변수 값의 기본 상태(사용 또는 사용 안 하도록 설정되어 있는지 여부)를 확인합니다.
- 해당 제품 목록 및 셀프 서비스 구매를 사용할 수 있는지 여부 보기
- 특정 제품의 현재 설정을 보거나 수정하여 특정 제품을 사용하거나 사용하지 않도록 설정

## <a name="requirements"></a>요구 사항

**MSCommerce** PowerShell 모듈을 사용하려면 다음이 필요합니다.

- Windows 10 장치
- PowerShell 5 이하. 현재 이 모듈에서는 PowerShell 6.x/7.x가 지원되지 않습니다.
- 장치에 대한 관리자 권한
- 테넌트에 대한 전역 또는 청구 관리자 역할

## <a name="install-the-mscommerce-powershell-module"></a>MSCommerce PowerShell 모듈 설치

**MSCommerce** PowerShell 모듈을 Windows 10 장치에 설치한 다음 시작할 각 PowerShell 세션으로 가져올 수 있습니다. PowerShell **갤러리에서 MSCommerce** [PowerShell 모듈을 다운로드합니다.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

**PowerShellGet을** 사용하여 **MSCommerce** PowerShell 모듈을 설치하려면 다음 명령을 실행합니다.

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>PowerShell 세션으로 MSCommerce 가져오기

Windows 10 장치에 모듈을 설치한 후 시작하는 각 PowerShell 세션으로 모듈을 가져와야 합니다. PowerShell 세션으로 가져오기 위해 다음 명령을 실행합니다.

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>커넥트 사용하여 MSCommerce에 연결

자격 증명을 사용하여 PowerShell 모듈에 연결하기 위해 다음 명령을 실행합니다.

```powershell
Connect-MSCommerce
```

이 명령은 현재 PowerShell 세션을 Azure Active Directory 연결합니다. 이 명령은 연결할 테넌트의 사용자 이름과 암호를 묻는 메시지를 제공합니다. 자격 증명에 대해 다단계 인증을 사용하도록 설정한 경우 대화형 옵션을 사용하여 로그인합니다.

## <a name="view-details-for-allowselfservicepurchase"></a>AllowSelfServicePurchase에 대한 세부 정보 보기

조직에 따라 **AllowSelfServicePurchase** 매개 변수 값 및 기본 상태에 대한 설명을 확인하도록 다음 명령을 실행합니다.

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>셀프 서비스 구매 제품 및 상태 목록 보기

사용 가능한 모든 셀프 서비스 구매 제품 목록과 각 제품의 상태를 확인한 후 다음 명령을 실행합니다.

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

다음 표에는 사용 가능한 제품과 **해당 ProductId가 나열됩니다.**

| 제품 | ProductId |
|-----------------------------|--------------|
| Power Apps 사용자당 수 | CFQ7TTC0KP0P |
| Power Automate 사용자당 수 | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium(독립 실행형) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project 플랜 1 | CFQ7TTC0KXND |
| Project 플랜 3 | CFQ7TTC0KXNC |
| Visio 플랜 1 | CFQ7TTC0KXN9 |
| Visio Plan 2 | CFQ7TTC0KXN8 |
| Windows 365 Enterprise | CFQ7TTC0HHS9 |
| Windows 365 Business | CFQ7TTC0J203 |
| Windows 하이브리드 혜택이 있는 Windows 365 Business | CFQ7TTC0HX99 |
## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>AllowSelfServicePurchase의 상태 보기 또는 설정

셀프 서비스 구매에 사용할 수 있는 제품 목록을 보고 나면 특정 제품의 설정을 보거나 수정할 수 있습니다.

특정 제품에 대한 정책 설정을 얻었다면 다음 명령을 실행합니다.

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

특정 제품에 대해 정책 설정을 사용하도록 설정하려면 다음 명령을 실행합니다.

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

특정 제품에 대한 정책 설정을 사용하지 않도록 설정하기 위해 다음 명령을 실행합니다.

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>AllowSelfServicePurchase를 사용하지 않도록 설정하는 예제 스크립트

다음 예제에서는 **MSCommerce** 모듈을 가져오고, 계정으로 로그인하고, Power Automate **대한 ProductId를** 가져온 다음 해당 제품에 대해 **AllowSelfServicePurchase를** 사용하지 않도록 설정하는 방법을 제공합니다.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

제품에 값이 여러 개 있는 경우 다음 예제와 같이 각 값에 대해 명령을 개별적으로 실행할 수 있습니다.

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[0].ProductID -Enabled $false
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[1].ProductID -Enabled $false
```


## <a name="troubleshooting"></a>문제 해결

### <a name="problem"></a>문제

다음과 같은 오류 메시지가 표시됩니다.

> HandleError : PolicyId 'AllowSelfServicePurchase', ErrorMessage를 사용하여 정책을 검색하지 못했습니다. - 연결이 닫혔습니다. 보내기 시 예기치 않은 오류가 발생했습니다.

이전 버전의 TLS(전송 계층 보안) 때문일 수 있습니다. 이 서비스를 연결하려면 TLS 1.2 이상을 사용해야 합니다.

### <a name="solution"></a>해결 방법

TLS 1.2로 업그레이드합니다. 다음 구문은 ServicePointManager 보안 프로토콜을 TLS1.2로 업데이트합니다.

```powershell
 [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.SecurityProtocolType]::Tls12
```

자세한 내용은 [TLS 1.2를 사용하도록](/mem/configmgr/core/plan-design/security/enable-tls-1-2)설정하는 방법을 참조합니다.

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a>관련 콘텐츠

[셀프 서비스 구매 관리(관리자)(문서)](manage-self-service-purchases-admins.md)

[셀프 서비스 구매 FAQ(문서)](self-service-purchase-faq.yml)
