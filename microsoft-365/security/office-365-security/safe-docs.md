---
title: Office 365 ATP의 안전한 문서
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Microsoft 365 E5 또는 Microsoft 365 E5 Security의 안전한 문서에 대해 알아보세요.
ms.openlocfilehash: cd689099fc6a6caa1e0e649c3f152f1de123bf12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827472"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5의 안전한 문서

안전한 문서는 Microsoft [Defender Advanced Threat Protection을](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 사용하여 제한된 보기에서 열린 문서 및 파일을 검사하는 Microsoft 365 E5 또는 Microsoft 365 E5 Security의 [기능입니다.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 안전한 문서는 이제 Office 버전 2004(12730.x) 이상인 사용자가 일반적으로 사용할 수 있습니다. 기본적으로 이 기능은 꺼져 있습니다. 보안 관리자가 사용하도록 설정해야 합니다.

- 이 기능은 *Microsoft 365 E5 또는 Microsoft 365 E5* 보안 라이선스(Office *365* ATP 요금제에는 포함되지 않음)를 사용하는 사용자만 사용할 수 있습니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다. 안전 문서를 사용하도록 설정하고 구성하려면 조직 관리 또는 보안 **관리자 역할 그룹의** **구성원이어야** 합니다. 보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

## <a name="how-does-microsoft-handle-your-data"></a>Microsoft에서 데이터를 어떻게 처리하나요?

안전한 보호를 위해 안전한 문서는 분석을 위해 [Microsoft Defender Advanced Threat Protection 클라우드로 파일을](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 보냅니다.

- Microsoft Defender Advanced Threat Protection에서 데이터를 처리하는 방법에 대한 세부 정보는 다음을 [참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- 위의 지침 외에 안전한 문서를 보낸 파일은 분석에 필요한 시간을 초과하여 Defender에 유지되지 않습니다. 일반적으로 24시간 이내

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>보안 그룹 규정 & 사용하여 안전한 문서 구성

1. 보안 그룹 & 센터를 <https://protection.office.com> 엽니다.

2. 위협 **관리 정책** \> **Policy** \> **ATP 안전 첨부 파일로 이동합니다.**

3. Office 응용 **프로그램 의 제한된 보기 외부에서 제한된 보기** 외부에서 열려는 경우 도움말 사용자의 안전성이 유지됩니다.

   - **Office 클라이언트에 대한 안전한 문서 사용**

   - **안전한 문서가 해당 파일을 악의적인 파일로**식별하는 경우에도 사용자가 제한된 보기를 클릭할 수 있도록 허용: 이 옵션을 사용하도록 설정하지 않는 것이 좋습니다.

4. 작업을 마쳤으면 **저장**을 클릭합니다.

![ATP 안전한 첨부 파일 페이지](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 수신 허용 문서 구성

다음 구문을 사용합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs 매개 변수는_ 전체 조직에 대해 안전한 문서를 사용하거나 사용하지 않도록 설정합니다.

- _AllowSafeDocsOpen_ 매개 변수는 문서가 악의적인 보기로 확인된 경우 사용자가 제한된 보기를 그만두는 것, 즉 문서 열기를 허용하거나 차단합니다.

이 예에서는 전체 조직에 대해 안전한 문서를 사용하도록 설정하고 사용자가 악의적인 보기에서 열지 못하도록 합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

### <a name="how-do-i-know-this-worked"></a>작동 여부는 어떻게 확인합니까?

안전 허용 문서가 사용하도록 설정및 구성되었는지 확인하려면 다음 단계를 수행합니다.

- 보안 & 규정 준수 센터에서 **위협 관리 정책** ATP 안전한 첨부 파일로 이동한 후 Office 응용 프로그램의 외부에서 제한된 보기를 열 기대해하는 파일을 신뢰하는 경우 도움말 사용자의 \> **Policy** \> **ATP Safe Attachments** **선택 사항이 안전하게 유지되는지 확인합니다.**

- Exchange Online PowerShell에서 다음 명령을 실행하고 속성 값을 확인합니다.

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
