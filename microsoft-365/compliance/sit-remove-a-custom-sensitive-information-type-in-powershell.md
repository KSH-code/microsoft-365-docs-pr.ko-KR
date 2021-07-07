---
title: PowerShell을 사용하여 사용자 지정 중요한 정보 유형 제거
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
description: PowerShell을 사용하여 사용자 지정 중요한 정보 유형을 제거하는 방법을 학습
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322953"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="42037-103">PowerShell을 사용하여 사용자 지정 중요한 정보 유형 제거</span><span class="sxs-lookup"><span data-stu-id="42037-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="42037-104">규정 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형을 제거하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42037-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="42037-105">**개별 사용자 지정 중요한 정보 유형** 제거: [PowerShell을](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)사용하여 사용자 지정 중요한 정보 유형 수정에 설명된 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="42037-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="42037-106">사용자 지정 중요한 정보 유형이 포함된 사용자 지정 규칙 패키지를 내보내고, XML 파일에서 중요한 정보 유형을 제거하고, 업데이트된 XML 파일을 기존 사용자 지정 규칙 패키지로 다시 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42037-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="42037-107">**사용자 지정 규칙 패키지 및 여기에 포함된 모든 사용자 지정 중요한 정보 유형 제거**: 이 방법은 이 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42037-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="42037-108">사용자 지정 중요한 정보 유형을 제거하기 전에 DLP 정책이나 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)이 중요한 정보 유형을 계속 참조하지 않는 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="42037-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. [<span data-ttu-id="42037-109">규정 준수 센터 PowerShell에 연결하기</span><span class="sxs-lookup"><span data-stu-id="42037-109">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="42037-110">사용자 지정 규칙 패키지를 제거하려면 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="42037-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="42037-111">Name 값(모든 언어) 또는 `RulePack id` (GUID) 값을 사용하여 규칙 패키지를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42037-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="42037-112">이 예제에서는 "Employee ID Custom Rule Pack"이라는 규칙 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="42037-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="42037-113">구문과 매개 변수에 대한 자세한 내용은 [제거-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42037-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="42037-114">사용자 지정 중요한 정보 유형을 성공적으로 제거했는지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="42037-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="42037-115">[DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet을 실행하고 이 규칙 패키지가 더 이상 나열되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="42037-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="42037-116">[DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 제거된 규칙 패키지에서 더 이상 중요한 정보 유형이 나열되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="42037-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="42037-117">사용자 지정 중요한 정보 유형의 경우 게시자 속성 값은 Microsoft Corporation이 아닌 다른 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42037-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="42037-118">\<Name\>(을)를 중요한 정보 유형의 이름 값(예: 직원 ID)으로 바꾸고 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 중요한 정보 유형이 더 이상 나열되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="42037-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="42037-119">추가 정보</span><span class="sxs-lookup"><span data-stu-id="42037-119">More information</span></span>

- [<span data-ttu-id="42037-120">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="42037-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="42037-121">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="42037-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="42037-122">DLP 함수가 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="42037-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
