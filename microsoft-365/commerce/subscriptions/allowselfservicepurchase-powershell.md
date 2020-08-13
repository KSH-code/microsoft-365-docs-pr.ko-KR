---
title: MSCommerce PowerShell 모듈에 대해 AllowSelfServicePurchase 사용
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: AllowSelfServicePurchase PowerShell cmdlet을 사용 하 여 셀프 서비스 구매를 설정 하거나 해제 하는 방법을 알아봅니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653716"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>MSCommerce PowerShell 모듈에 대해 AllowSelfServicePurchase 사용

이제 [Powershell 갤러리](https://aka.ms/allowselfservicepurchase-powershell-gallery)에서 **MSCommerce** powershell 모듈을 사용할 수 있습니다. 이 모듈에는 조직의 사용자가 셀프 서비스 구매를 수행할 수 있는지 여부를 제어 하는 **AllowSelfServicePurchase** 에 대 한 **policyid** 매개 변수 값이 포함 되어 있습니다.

**MSCommerce** PowerShell 모듈을 사용 하 여 다음을 수행할 수 있습니다.

- 사용 하거나 사용 하지 않도록 설정 되었는지 여부에 관계 없이 **AllowSelfServicePurchase** 매개 변수 값의 기본 상태를 확인 합니다.
- 해당 하는 제품 목록 및 셀프 서비스 구매가 사용 하도록 설정 되었는지 여부 확인
- 특정 제품에 대 한 현재 설정을 보거나 수정 하 여 사용 하거나 사용 하지 않도록 설정

## <a name="requirements"></a>요구 사항

**MSCommerce** PowerShell 모듈을 사용 하려면 다음이 필요 합니다.

- Windows 10 장치
- 장치에 대 한 관리자 권한
- 테 넌 트에 대 한 전역 또는 대금 청구 관리자 역할

## <a name="install-the-mscommerce-powershell-module"></a>MSCommerce PowerShell 모듈 설치

Windows 10 장치에 **MSCommerce** PowerShell 모듈을 한 번 설치 하 고 시작한 각 powershell 세션으로 가져옵니다. [Powershell 갤러리](https://aka.ms/allowselfservicepurchase-powershell-gallery)에서 **MSCommerce** PowerShell 모듈을 다운로드 합니다.

**PowerShellGet**을 사용 하 여 **MSCommerce** PowerShell 모듈을 설치 하려면 다음 명령을 실행 합니다.

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>PowerShell 세션으로 MSCommerce 가져오기

Windows 10 장치에 모듈을 설치한 후에는이를 시작 하는 각 PowerShell 세션으로 가져옵니다. 이를 PowerShell 세션으로 가져오려면 다음 명령을 실행 합니다.

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>자격 증명을 사용 하 여 MSCommerce에 연결

자격 증명을 사용 하 여 PowerShell 모듈에 연결 하려면 다음 명령을 실행 합니다.

```powershell
Connect-MSCommerce
```

이 명령은 현재 PowerShell 세션을 Azure Active Directory 테 넌 트에 연결 합니다. 이 명령은 연결 하려는 테 넌 트의 사용자 이름과 암호를 입력 하 라는 메시지를 표시 합니다. 자격 증명에 multi-factor authentication을 사용 하도록 설정 된 경우 대화형 옵션을 사용 하 여 로그인 합니다.

## <a name="view-details-for-allowselfservicepurchase"></a>AllowSelfServicePurchase에 대 한 세부 정보 보기

조직에 따라 **AllowSelfServicePurchase** 매개 변수 값 및 기본 상태에 대 한 설명을 보려면 다음 명령을 실행 합니다.

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>셀프 서비스 구매 제품 및 해당 상태 목록 보기

사용 가능한 모든 셀프 서비스 구매 제품의 목록과 각 상태를 보려면 다음 명령을 실행 합니다.

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

다음 표에는 사용 가능한 제품 및 해당 **ProductId**가 나와 있습니다.

| 제품 | 제품 |
|-----------------------------|--------------|
| 사용자 당 전원 앱 | CFQ7TTC0KP0P |
| 사용자 당 전원 자동화 | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |
| 프로젝트 계획 1 | CFQ7TTC0KXND |
| 프로젝트 계획 3 | CFQ7TTC0KXNC |
| Visio 계획 1 | CFQ7TTC0KXN9 |
| Visio 계획 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>AllowSelfServicePurchase의 상태를 보거나 설정 합니다.

셀프 서비스 구매에 사용할 수 있는 제품 목록을 확인 한 후에는 특정 제품에 대 한 설정을 보거나 수정할 수 있습니다.

특정 제품에 대 한 정책 설정을 가져오려면 다음 명령을 실행 합니다.

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

특정 제품에 대 한 정책 설정을 사용 하도록 설정 하려면 다음 명령을 실행 합니다.

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

특정 제품에 대 한 정책 설정을 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>AllowSelfServicePurchase을 사용 하지 않도록 설정 하는 스크립트 예제

다음은 **MSCommerce** 모듈을 가져오고, 계정으로 로그인 하 고, 전원 자동화를 위해 제품 **일련번호** 를 가져온 후 해당 제품에 대해 **AllowSelfServicePurchase** 를 사용 하지 않도록 설정 하는 방법을 보여 주는 예제입니다.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>문제 해결

### <a name="problem"></a>데

다음과 같은 오류 메시지가 표시 됩니다.

> HandleError: PolicyId가 ' AllowSelfServicePurchase ' 인 정책을 검색 하지 못했습니다. ErrorMessage-기본 연결이 닫혔습니다. 보내기에서 예기치 않은 오류가 발생 했습니다.

이전 버전의 TLS (전송 계층 보안)로 인 한 것일 수 있습니다. 이 서비스에 연결 하려면 TLS 1.2 이상을 사용 해야 합니다.

### <a name="solution"></a>해결 방법

TLS 1.2으로 업그레이드 합니다.[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
