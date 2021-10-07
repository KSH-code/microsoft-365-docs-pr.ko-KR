---
title: 문서 지문
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
ms.localizationpriority: medium
description: 조직에서 정보 근로자는 일상적으로 다양한 종류의 중요한 정보를 처리합니다. 문서 지문을 사용하면 조직 전체에서 사용되는 표준 양식을 식별하여 이 정보를 보다 쉽게 보호할 수 있습니다. 이 항목에서는 문서 지문의 개념과 PowerShell을 사용하여 지문을 만드는 방법에 대해 설명합니다.
ms.openlocfilehash: 6661fd52bfe94ab23a38eaa42eca45a3e609c565
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60155049"
---
# <a name="document-fingerprinting"></a>문서 지문

조직에서 정보 근로자는 일상적으로 다양한 종류의 중요한 정보를 처리합니다. 보안 및 준수 센터에서 문서 지문을 사용하면 조직 전체에서 사용되는 표준 양식을 식별하여 이 정보를 보다 쉽게 &amp; 보호할 수 있습니다. 이 항목에서는 문서 지문의 개념과 PowerShell을 사용하여 지문을 만드는 방법에 대해 설명합니다.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>문서 지문 관련 기본 시나리오

문서 지문은 표준 양식을 중요한 정보 유형으로 변환하는 DLP(데이터 손실 방지) 기능으로, DLP 정책 규칙에서 사용할 수 있습니다. 예를 들어 빈 특허 템플릿을 기반으로 문서 지문을 만든 다음 중요한 콘텐츠가 채워진 모든 발신 특허 템플릿을 검색하고 차단하는 DLP 정책을 만들 수 있습니다. 선택적으로 보낸 사람에게 [](use-notifications-and-policy-tips.md) 중요한 정보를 보낼 수 있는 경우를 알리는 정책 팁을 설정할 수 있으며, 보낸 사람은 받는 사람이 특허를 받을 자격이 있는지 확인해야 합니다. 이 프로세스는 조직에서 사용되는 텍스트 기반 양식에서 작동합니다. 업로드할 수 있는 양식의 추가 예는 다음과 같습니다.
  
- 정부 양식
- HIPAA(Health Insurance Portability and Accountability Act) 준수 양식  
- 인사 부서의 직원 정보 양식
- 조직용으로 특수 작성된 사용자 지정 양식

조직에서 특정 양식을 사용하여 중요한 정보를 전송하는 업무 관행을 이미 설정한 상태인 것이 가장 좋습니다. 문서 지문으로 변환할 빈 양식을 업로드하고 해당 정책을 설정한 후 DLP는 아웃바운드 메일에서 해당 지문과 일치하는 문서를 검색합니다.

## <a name="how-document-fingerprinting-works"></a>문서 지문의 작동 방식

문서에 실제 지문이 포함되는 것은 아니며 지문과 같은 기능이 제공됩니다. 사람의 지문에 고유한 패턴이 있는 것처럼 문서에도 고유한 단어 패턴이 있습니다. 파일을 업로드할 때 DLP는 문서의 고유한 단어 패턴을 식별하고, 해당 패턴을 기반으로 문서 지문을 만들고, 해당 문서 지문을 사용하여 동일한 패턴이 포함된 아웃바운드 문서를 검색합니다. 따라서 양식이나 서식 파일을 업로드하면 가장 효율적인 유형의 문서 지문을 만들 수 있습니다. 양식을 작성하는 모든 사용자는 동일한 원본 단어 집합을 사용하게 되며, 원하는 단어를 문서에 추가합니다. 아웃바운드 문서가 암호로 보호되지 않은 경우 원본 양식의 모든 텍스트가 포함된 경우 DLP는 문서가 문서 지문과 일치하는지 확인할 수 있습니다.

> [!IMPORTANT]
> 현재 DLP는 온라인에서만 문서 지문을 검색 Exchange 있습니다.

다음 예에서는 특허 서식 파일을 기준으로 문서 지문을 만들 때 수행되는 작업을 설명하지만 원하는 모든 양식을 기준으로 문서 지문을 만들 수 있습니다.
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>특허 서식 파일의 문서 지문과 일치하는 특허 문서의 예

![문서 지문 다이어그램](../media/Document-Fingerprinting-diagram.png)
  
특허 서식 파일에는 "특허 제목", "인벤터스" 및 "설명" 및 각 필드에 대한 설명(단어 패턴)이 포함되어 있습니다. 원래 특허 템플릿을 업로드할 때 지원되는 파일 형식 중 하나와 일반 텍스트로 표시됩니다. DLP는 이 단어 패턴을 문서 지문으로 변환합니다. 이 파일은 원본 텍스트를 나타내는 고유한 해시 값을 포함하는 작은 유니코드 XML 파일로, 지문은 Active Directory에서 데이터 분류로 저장됩니다. 보안 조치로 원본 문서 자체는 서비스에 저장되지 않습니다. 해시 값만 저장되고 원본 문서는 해시 값으로 재구성할 수 없습니다. 그러면 특허 지문이 DLP 정책과 연결될 수 있는 중요한 정보 유형이 됩니다. 지문을 DLP 정책과 연결한 후 DLP는 특허 지문과 일치하는 문서가 포함된 아웃바운드 전자 메일을 검색하고 조직의 정책에 따라 해당 전자 메일을 처리합니다. 

예를 들어 일반 직원이 특허가 포함된 발신 메시지를 보내지 못하도록 하는 DLP 정책을 설정할 수 있습니다. DLP는 특허 지문을 사용하여 특허를 검색하고 해당 전자 메일을 차단합니다. 또는 법률 부서에서 비즈니스상 필요한 특허를 다른 조직에 보낼 수 있도록 할 수 있습니다. 특정 부서에서 DLP 정책에서 해당 부서에 대한 예외를 만들어 중요한 정보를 보내거나 업무 정당성으로 정책 팁을 다시 정의하도록 허용할 수 있습니다.
  
### <a name="supported-file-types"></a>지원되는 파일 형식

문서 지문은 메일 흐름 규칙에서 지원되는 동일한 파일 형식(전송 규칙)을 지원합니다. 지원되는 파일 형식 목록은 메일 흐름 규칙 콘텐츠 검사에 지원되는 파일 [형식을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection) 파일 형식에 대한 한 가지 빠른 참고 사항: 메일 흐름 규칙과 문서 지문 모두 .dotx 파일 형식을 지원하지 않습니다. 이는 Word의 서식 파일이기 때문에 혼동을 주게 될 수 있습니다. 이 항목 및 기타 문서 지문 항목에서 "template"이라는 단어가 표시되면 서식 파일 형식이 아니라 표준 양식으로 설정한 문서를 참조합니다.
  
#### <a name="limitations-of-document-fingerprinting"></a>문서 지문의 제한

문서 지문은 다음과 같은 경우 중요한 정보를 검색하지 않습니다.
  
- 암호로 보호된 파일
- 이미지만 포함된 파일
- 문서 지문을 만드는 데 사용된 원본 양식의 모든 텍스트가 포함되지 않는 문서
- 10MB보다 큰 파일

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>PowerShell을 사용하여 문서 지문을 기반으로 분류 규칙 패키지 만들기

현재 보안 및 준수 센터에서 PowerShell을 사용하여 문서 지문을 만들 &amp; 수 있습니다. 연결하기 위해 보안 커넥트 준수 센터 [PowerShell에 & 참조합니다.](/powershell/exchange/connect-to-scc-powershell)

DLP는 분류 규칙 패키지를 사용하여 중요한 콘텐츠를 검색합니다. 문서 지문을 기반으로 분류 규칙 패키지를 만들 경우 **New-DlpFingerprint** 및 **New-DlpSensitiveInformationType** cmdlet을 사용 합니다. **New-DlpFingerprint의** 결과는 데이터 분류 규칙 외부에 저장되지 않는 것이기 때문에 항상 같은 PowerShell 세션에서 **New-DlpFingerprint** 및 **New-DlpSensitiveInformationType** 또는 **Set-DlpSensitiveInformationType을** 실행합니다. 다음 예에서는 C:\My Documents\Contoso Employee Template.docx 파일을 기반으로 새 문서 지문을 만듭니다. 새 지문을 변수로 저장하여 동일한 PowerShell 세션에서 **New-DlpSensitiveInformationType** cmdlet과 함께 사용할 수 있습니다.
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

C:\My Documents\Contoso Customer Information Form.docx 파일의 문서 지문을 사용하는 "Contoso Employee Confidential"이라는 새 데이터 분류 규칙을 만들어 보겠습니다.
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

이제 **Get-DlpSensitiveInformationType** cmdlet을 사용하여 모든 DLP 데이터 분류 규칙 패키지를 찾을 수 있으며, 이 예에서 "Contoso Customer Confidential"은 데이터 분류 규칙 패키지 목록의 일부입니다. 
  
마지막으로 보안 및 준수 센터의 DLP 정책에 "Contoso Customer Confidential" 데이터 분류 규칙 &amp; 패키지를 추가합니다. 이 예에서는 "ConfidentialPolicy"라는 기존 DLP 정책에 규칙을 추가합니다.

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

다음 예와 같이 데이터 분류 규칙 패키지를 Exchange Online 메일 흐름 규칙에 사용할 수도 있습니다. 이 명령을 실행하려면 먼저 [PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell)커넥트 Exchange Online 합니다. 또한 규칙 패키지가 보안 및 준수 센터에서 보안 준수 센터로 동기화되는 데 Exchange &amp; 있습니다.
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

이제 DLP는 Contoso Customer 및 문서 지문과 Form.docx 검색합니다.
  
구문과 매개 변수 정보는 다음을 참조하세요.

- [New-DlpFingerprint](/powershell/module/exchange/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](/powershell/module/exchange/Get-DlpSensitiveInformationType)
