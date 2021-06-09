---
title: 키워드 사전 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Office 365 보안 및 준수 센터에서 키워드 사전을 만드는 기본 단계에 대해 알아봅니다.
ms.openlocfilehash: 1e1aa45c3bf4d31e4c969b0bc0949109fa716467
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841165"
---
# <a name="create-a-keyword-dictionary"></a>키워드 사전 만들기

DLP(데이터 손실 방지)는 중요한 항목을 식별, 모니터링 및 보호할 수 있습니다. 중요한 항목을 식별하려면 키워드를 찾아야 하는 경우가 있으며, 특히 의료 관련 통신과 같은 일반 컨텐츠 또는 부적절하거나 명시적인 언어를 식별해야 합니다. 중요한 정보 유형에서 키워드 목록을 만들 수 있지만 키워드 목록은 크기가 제한되어 있으며, 키워드 목록을 만들거나 편집하려면 XML을 수정해야 합니다. 키워드 사전은 키워드 관리를 보다 간단하고 훨씬 더 큰 규모로 제공하여 사전에서 최대 1 MB의 용어(사후 압축)를 지원하고 모든 언어를 지원합니다. 테넌트 제한도 압축 후에 1 MB가 됩니다. 1 MB의 사후 압축 제한은 테넌트 전체에서 결합된 모든 사전에 1백만 문자에 가까운 문자가 있을 수 있음을 의미합니다.

## <a name="keyword-dictionary-limits"></a>키워드 사전 제한

테넌트당 만들 수 있는 중요한 정보 유형을 기반으로 하는 키워드 사전은 50개로 제한됩니다. 테넌트에 있는 키워드 사전의 수를 확인하려면 [보안 및 준수 센터 PowerShell 연결](/powershell/exchange/connect-to-scc-powershell)의 절차를 따라 테넌트에 연결하고 이 PowerShell 스크립트를 실행합니다.

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>키워드 사전을 만드는 기본 단계

사전의 키워드는 다양한 원본, 서비스 또는 PowerShell cmdlet에서 가져온 파일(예:.csv 또는 .txt 목록)(대부분의 경우), PowerShell cmdlet에 사용자가 직접 입력한 목록 또는 기존 사전에서 가져올 수 있습니다. 키워드 사전을 만들 때 다음과 같은 동일한 핵심 단계를 따르세요.
  
1. **보안 및 규정 준수 센터**([https://protection.office.com](https://protection.office.com))를 사용하거나 **보안 &amp;준수 센터 PowerShell** 에 연결합니다.
    
2. **원하는 원본** 에서 키워드를 정의 하거나 로드할 수 있습니다. 마법사와 cmdlet 모두 쉼표로 구분된 키워드 목록을 사용하여 사용자 정의 키워드 사전을 만들 수 있으므로 이 단계는 키워드의 출처에 따라 약간 다릅니다. 로드되면 가져오기 전에 인코딩 및 바이트 배열로 변환됩니다.
    
3. **사전을 만듭니다**. 이름과 설명을 선택하고 사전을 만듭니다.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>보안 및 준수 센터를 사용하여 키워드 사전을 만듭니다.

다음 단계를 따라 사용자 지정 사전에 대한 키워드를 만들고 가져오세요.

1. 보안 및 규정 준수 센터([https://protection.office.com](https://protection.office.com))에 연결합니다.

2. **분류 > 중요한 정보 유형** 으로 이동합니다.

3. **만들기** 를 선택하고 중요한 정보 유형에 대한 **이름** 및 **설명** 을 입력하고 **다음** 을 선택합니다.

4. **요소 추가** 를 선택한 다음 **다음이 포함된 내용 감지** 드롭다운에서 **사전(광범위한 키워드)** 을 선택합니다.

5. **사전 추가** 를 선택합니다.

6. 검색 컨트롤에서 **여기에서 새 키워드 사전을 만들 수 있음** 을 선택합니다.

7. 사용자 지정 사전에 대한 **이름** 을 입력합니다.

8. **가져오기** 를 선택하고 키워드 파일 종류에 따라 **텍스트 파일에서** 또는 **csv 파일에서** 중 하나를 선택합니다.

9. 파일 대화 상자에서 로컬 PC 또는 네트워크 파일 공유에 있는 키워드 파일을 선택한 다음 **열기** 를 선택합니다.

10. **저장** 을 선택한 다음 **키워드 사전** 목록에서 사용자 지정 사전을 선택합니다.

11. **추가** 를 선택하고 **다음** 을 선택합니다.

12. 중요한 정보 유형 선택 사항을 검토 및 완료한 다음 **완료** 를 선택합니다.
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>PowerShell을 사용하여 파일에서 키워드 사전 만들기

대형 사전을 작성해야 하는 경우 파일 또는 다른 원본에서 내보낸 목록의 키워드를 사용하는 경우가 많습니다. 이 경우 외부 전자 메일에서 표시하기에 부적절한 언어 목록이 포함된 키워드 사전을 만듭니다. 먼저 [보안 &amp; 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)에 연결해야 합니다.
  
1. 키워드를 텍스트 파일에 복사합니다. 이때 각 키워드를 별도 줄에 복사해야 합니다.
    
2. 텍스트 파일을 유니코드 인코딩으로 저장합니다. 메모장에서 \> **다른 이름으로 저장** \> **인코딩으로** \> **유니코드** 를 선택합니다.
    
3. 다음 cmdlet을 실행하여 파일을 변수로 읽습니다.
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. 다음 cmdlet을 실행하여 사전을 만듭니다.
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>사용자 지정 중요한 정보 유형과 DLP 정책에서 키워드 사전 사용

키워드 사전은 사용자 정의 중요한 정보 유형에 대한 일치 요구 사항의 일부로 사용하거나 중요한 정보 유형 자체로 사용할 수 있습니다. 둘 다 [사용자 지정 중요한 정보 유형](create-a-custom-sensitive-information-type-in-scc-powershell.md)을(를) 생성해야 합니다. 링크된 문서의 지침에 따라 중요한 정보 유형을 만듭니다. XML을 사용하게 되면 사전에 사용할 GUID 식별자가 필요합니다.
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

사전의 ID를 확인하려면 다음 명령을 실행하고 **Identity** 속성 값을 복사합니다. 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

이 명령의 출력은 다음과 같습니다.
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


사용자 지정 중요한 정보 유형의 XML에 ID를 붙여넣은 후 업로드합니다. 이제 사전이 중요한 정보 유형 목록에 표시되므로 일치시킬 키워드 수를 지정하여 정책에서 바로 사용할 수 있습니다.
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```

> [!NOTE]
> Microsoft 365 Information Protection은 다음에 대해 미리 보기 더블 바이트 문자 집합 언어를 지원합니다.
> - 중국어(간체)
> - 중국어(번체)
> - 한국어
> - 일본어
>
>이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다. 자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.
