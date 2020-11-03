---
title: Microsoft Defender for Office 365의 안전 문서
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
description: Microsoft 365 E5 또는 Microsoft 365 E5 보안의 안전 문서에 대해 알아봅니다.
ms.openlocfilehash: 7fbee440298aea3609665b62a946ae3ce2857e37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845483"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5에서 안전한 문서

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


안전한 문서는 microsoft 365 E5 또는 microsoft 365 E5 보안 기능으로, [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 를 사용 하 여 [제한 된 보기](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)에서 열린 문서와 파일을 검사 합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 안전한 문서는 *microsoft 365 e5* 또는 *Microsoft 365 e5 보안* 라이선스가 있는 사용자만 사용할 수 있습니다. 이러한 라이선스는 Microsoft Defender for Office 365 계획에 포함 되어 있지 않습니다.

- 안전한 문서는 Microsoft 365 Apps for enterprise (이전 명칭: Office 365 ProPlus) 버전 2004 이상에서 지원 됩니다.

- <https://protection.office.com>에서 보안 및 준수 센터를 엽니다. **ATP 안전한 첨부 파일** 페이지로 바로 이동 하려면를 엽니다 <https://protection.office.com/safeattachmentv2> .

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 항목의 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다. 안전한 문서를 사용 하도록 설정 하 고 구성 하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다. 보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft에서 데이터를 처리 하는 방법

보호를 유지 하기 위해 안전한 문서는 [Microsoft Defender For Endpoint cloud for](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) analysis로 파일을 보냅니다. 끝점에 대 한 Microsoft Defender에서 데이터를 검색 하는 방법에 대 한 자세한 내용은 [Microsoft defender For endpoint data 저장 및 개인 정보](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)를 참조 하세요.

안전한 문서로 보낸 파일은 분석에 필요한 시간 외에는 Defender에 보존 되지 않습니다 (일반적으로 24 시간 미만).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>보안 & 준수 센터를 사용 하 여 안전한 문서 구성

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동한 후 **전역 설정을** 클릭 합니다.

2. **전체 설정이** 표시 되 면 다음 설정을 구성 합니다.

   - **Office 클라이언트에 대 한 안전 문서 설정** : 오른쪽으로 이동을 이동 하 여 기능을 설정 합니다. ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

   - **안전한 보기를 클릭 하는 것을 허용 하는 경우에도 안전 문서에서 해당 파일을 악성으로 식별** 함:이 옵션을 해제 하는 것이 좋습니다 (왼쪽으로 전환: 설정/해제 상태 그대로 둠 ![ ](../../media/scc-toggle-off.png) ).

   작업을 마쳤으면 **저장** 을 클릭합니다.

   ![안전한 첨부 파일 페이지에서 전역 설정을 선택한 후에 안전한 문서 설정을 선택 합니다.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell을 사용 하 여 안전한 문서 구성

다음 구문을 사용합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ 매개 변수는 전체 조직에 대 한 안전한 문서를 사용 하거나 사용 하지 않도록 설정 합니다.
- 문서가 악성으로 식별 된 경우에는 _AllowSafeDocsOpen_ 매개 변수를 사용 하 여 사용자가 문서를 여는 제한 된 보기를 끝낼 수 있습니다.

이 예에서는 전체 조직에 대해 안전한 문서를 사용 하도록 설정 하 고 제한 된 보기에서 악의적으로 식별 된 문서를 사용자가 열지 못하도록 합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

구문 및 매개 변수에 대 한 자세한 내용은 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)를 참조 하십시오.

### <a name="how-do-i-know-this-worked"></a>작동 여부는 어떻게 확인합니까?

안전한 문서를 사용 하도록 설정 하 고 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.

- 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동 하 여 **전역 설정을** 클릭 하 고, **안전한 문서에서 해당 파일을 악성 설정으로 식별 하는 경우에도 사용자가 제한 된 보기를 클릭할 수 있도록** 합니다. **Turn on Safe Documents for Office clients**

- Exchange Online PowerShell에서 다음 명령을 실행 하 고 속성 값을 확인 합니다.

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 안전한 문서 보호를 테스트 하는 데 사용할 수 있는 파일은 다음과 같습니다. 이러한 문서는 맬웨어 방지 및 바이러스 백신 솔루션을 테스트 하기 위한 EICAR.TXT 파일과 비슷합니다. 파일이 손상 되는 것은 아니지만 안전한 문서 보호를 트리거합니다.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
