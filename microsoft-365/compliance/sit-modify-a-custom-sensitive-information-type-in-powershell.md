---
title: PowerShell을 사용하여 사용자 지정 중요한 정보 유형 수정
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: PowerShell을 사용하여 사용자 지정 중요한 정보를 수정하는 방법을 학습합니다.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322960"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="e3721-103">PowerShell을 사용하여 사용자 지정 중요한 정보 유형 수정</span><span class="sxs-lookup"><span data-stu-id="e3721-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="e3721-104">규정 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형을 수정하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="e3721-105">XML 파일에 사용자 지정 중요한 정보 유형을 포함하는 기존 규칙 패키지를 내보냅니다. (또는 기존 XML 파일이 있는 경우이를 내보냅니다)</span><span class="sxs-lookup"><span data-stu-id="e3721-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="e3721-106">내보낸 XML 파일의 사용자 지정 중요한 정보 유형을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="e3721-107">기존 규칙 패키지에 업데이트된 XML 파일을 다시 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="e3721-108">규정 준수 센터 PowerShell에 연결하려면 [규정 준수 센터 PowerShell에 연결하기](/powershell/exchange/exchange-online-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3721-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="e3721-109">1단계: XML 파일로 기존 규칙 패키지 내보내기</span><span class="sxs-lookup"><span data-stu-id="e3721-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="e3721-110">XML 파일의 복사본이 있는 경우(예: XML 파일을 만들고 가져온 경우) 다음 단계로 건너 뛰고 XML 파일을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="e3721-111">아직 모르는 경우 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 사용자 지정 규칙 패키지의 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="e3721-p101">기본 제공 민감한 정보 유형이 들어있는 기본 제공 규칙 패키지의 이름은 Microsoft Rule Package입니다. 규정 준수 센터 UI에서 만든 사용자 지정 중요한 정보 유형이 포함된 규칙 패키지의 이름은 Microsoft.SCCManaged.CustomRulePack입니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-p101">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="e3721-114">[DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet을 사용하여 사용자 지정 규칙 패키지를 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="e3721-115">예를 들어, 규칙 패키지의 이름이 "Employee ID Custom Rule Pack"인 경우 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="e3721-116">[Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet을 실행하여 사용자 지정 규칙 패키지를 XML 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="e3721-117">이 예제에서는 규칙 패키지를 C:\My Documents 폴더의 ExportedRulePackage.xml 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="e3721-118">2단계: 내보낸 XML 파일의 중요한 정보 유형 수정</span><span class="sxs-lookup"><span data-stu-id="e3721-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="e3721-119">XML 파일의 중요한 정보 유형 및 파일의 기타 요소는 이 항목의 앞부분에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="e3721-120">3단계: 기존 규칙 패키지에 업데이트된 XML 파일 다시 가져오기</span><span class="sxs-lookup"><span data-stu-id="e3721-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="e3721-121">업데이트된 XML을 기존 규칙 패키지로 가져오려면 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e3721-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="e3721-122">구문과 매개 변수에 대한 자세한 내용은 [설정-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3721-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="e3721-123">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e3721-123">More information</span></span>

- [<span data-ttu-id="e3721-124">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="e3721-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="e3721-125">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="e3721-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="e3721-126">DLP 함수가 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="e3721-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
