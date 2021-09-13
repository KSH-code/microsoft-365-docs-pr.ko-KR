---
title: PowerShell을 Microsoft 365 라이선스 및 서비스 보기
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: PowerShell을 사용하여 조직에서 사용할 수 있는 라이선스 계획, 서비스 및 라이선스에 대한 Microsoft 365 설명
ms.openlocfilehash: 920bc00dcfa774f7cf157be4a543bf30e18f406e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210385"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>PowerShell을 Microsoft 365 라이선스 및 서비스 보기

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

모든 Microsoft 365 구독은 다음 요소로 구성됩니다.

- **라이선스 계획** 이러한 계획을 라이선스 계획 또는 Microsoft 365 라고도 합니다. 라이선스 계획은 사용자가 Microsoft 365 서비스를 정의합니다. 사용자 Microsoft 365 여러 라이선스 요금제가 포함될 수 있습니다. 라이선스 계획의 예는 다음과 Microsoft 365 E3.
    
- **서비스** 이러한 계획을 서비스 계획라고도 합니다. 서비스는 Microsoft 365 계획(예: Exchange Online 및 엔터프라이즈용 Microsoft 365 앱(이전 명명된 Office 365 ProPlus)에서 사용할 수 있는 Office 365 ProPlus. 사용자는 다양 한 서비스에 대 한 액세스 권한을 부여 하는 다른 라이센스 계획에서 할당 된 여러 개의 라이센스를 가질 수 있습니다.
    
- **라이선스** 각 라이선스 계획에는 구입한 라이선스 수가 포함되어 있습니다. 라이선스 계획에 의해 정의된 Microsoft 365 서비스를 사용할 수 있도록 사용자에게 라이선스를 할당합니다. 모든 사용자 계정에는 라이선스 계획 하나에서 하나 이상의 라이선스가 필요하며, 따라서 라이선스가 라이선스에 로그온하여 서비스를 Microsoft 365 수 있습니다.
    
PowerShell을 사용하여 조직에서 사용 Microsoft 365 라이선스 계획, 라이선스 및 서비스에 대한 세부 정보를 볼 Microsoft 365 있습니다. 다른 Office 365 구독에서 사용할 수 있는 제품, 기능 및 서비스에 대한 자세한 내용은 Office 365 [계획 옵션을 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
현재 라이선스 계획 및 각 계획에 대해 사용 가능한 라이선스에 대한 요약 정보를 확인한 후 다음 명령을 실행합니다.
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

결과에는 다음이 포함되어 있습니다.
  
- **SkuPartNumber:** 조직에 사용할 수 있는 라이선스 계획을 보여줍니다. 예를 들어 E3의 라이선스 계획 `ENTERPRISEPACK` Office 365 Enterprise 있습니다.
    
- **사용:** 특정 라이선스 계획에 대해 구입한 라이선스 수입니다.
    
- **ConsumedUnits:** 특정 라이선스 계획에서 사용자에게 할당한 라이선스 수입니다.
    
모든 라이선스 계획에서 사용할 수 있는 Microsoft 365 서비스에 대한 세부 정보를 확인하기 위해 먼저 라이선스 계획 목록을 표시합니다.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

그런 다음 라이선스 계획 정보를 변수에 저장합니다.

```powershell
$licenses = Get-AzureADSubscribedSku
```

그런 다음 특정 라이선스 계획에 서비스를 표시합니다.

```powershell
$licenses[<index>].ServicePlans
```

\<index> 은 명령 표시에서 라이선스 계획의 행 번호를 지정하는 `Get-AzureADSubscribedSku | Select SkuPartNumber` 정수(1)입니다.

예를 들어 명령 표시가 다음과 `Get-AzureADSubscribedSku | Select SkuPartNumber` 같은 경우

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

그런 다음 ENTERPRISEPREMIUM 라이선스 계획에 대한 서비스를 표시하는 명령은 다음을 실행합니다.

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM은 세 번째 행입니다. 따라서 인덱스 값은 (3 - 1) 또는 2입니다.

라이선스 계획(제품 이름), 포함된 서비스 계획 및 해당 식별 이름의 전체 목록은 라이선스에 대한 제품 이름 및 서비스 계획 [식별자를 참조하세요.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 [테넌트 Microsoft 365 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

>[!Note]
>이 항목에서 설명하는 절차를 자동화하는 PowerShell 스크립트를 사용할 수 있습니다. 특히 이 스크립트를 사용하면 Sway를 포함하여 Microsoft 365 조직에서 서비스를 보고 사용하지 않도록 설정할 수 있습니다. 자세한 내용은 [PowerShell을 통해 Sway에 대한 액세스 사용 안 을 참조하세요.](disable-access-to-sway-with-microsoft-365-powershell.md)
>
    
현재 라이선스 계획 및 각 계획에 대해 사용 가능한 라이선스에 대한 요약 정보를 확인한 후 다음 명령을 실행합니다.
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol** 이 있는 cmdlet을 지원하지 않습니다. 이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.
>

결과에는 다음 정보가 포함됩니다.
  
- **AccountSkuId:** 구문을 사용하여 조직에 사용할 수 있는 라이선스 계획을 보여 주면 `<CompanyName>:<LicensingPlan>` 됩니다.  _\<CompanyName>_ 는 조직에 등록할 때 제공한 Microsoft 365 고유합니다. 값은 _\<LicensingPlan>_ 모든 사람에 대해 동일합니다. 예를 들어 값 에서 회사 이름은 입니다. 및 라이선스 계획 이름 `litwareinc:ENTERPRISEPACK` `litwareinc` 은 E3의 시스템 Office 365 Enterprise `ENTERPRISEPACK` 있습니다.
    
- **ActiveUnits:** 특정 라이선스 계획에 대해 구입한 라이선스 수입니다.
    
- **WarningUnits:** 라이선스 계획에서 갱신하지 않은 라이선스 수로, 30일 유예 기간이 경과하면 만료됩니다.
    
- **ConsumedUnits:** 특정 라이선스 계획에서 사용자에게 할당한 라이선스 수입니다.
    
모든 라이선스 계획에서 사용할 수 있는 Microsoft 365 서비스에 대한 세부 정보를 확인한 후 다음 명령을 실행합니다.
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

다음 표에는 서비스 Microsoft 365 가장 일반적인 서비스에 대한 이름 및 서비스 계획이 표시됩니다. 서비스 계획 목록이 다를 수도 있습니다. 
  
|**서비스 계획**|**설명**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |RMS(Azure 권한 관리)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |*엔터프라이즈용 Microsoft 365 앱(이전에는 Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |비즈니스용 Skype Online  <br/> |
| `SHAREPOINTWAC` <br/> |사무실  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online 계획 2  <br/> |
   
라이선스 계획(제품 이름), 포함된 서비스 계획 및 해당 식별 이름의 전체 목록은 라이선스에 대한 제품 이름 및 서비스 계획 [식별자를 참조하세요.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

특정 라이선스 계획에서 사용할 Microsoft 365 서비스에 대한 세부 정보를 확인한 후 다음 구문을 사용 합니다.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

이 예에서는 litwareinc:ENTERPRISEPACK(Office 365 Enterprise E3) 라이선스 계획에서 사용할 수 있는 서비스를 보여줍니다.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)