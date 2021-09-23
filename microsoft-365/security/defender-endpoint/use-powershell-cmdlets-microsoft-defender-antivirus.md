---
title: PowerShell cmdlet을 사용하여 구성 및 실행 Microsoft Defender 바이러스 백신
description: 이 Windows 10 PowerShell cmdlet을 사용하여 검색을 실행하고 보안 인텔리전스를 업데이트하고 설정을 변경할 수 Microsoft Defender 바이러스 백신.
keywords: 검사, 명령줄, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: e297eb169f3b71185cc6f8fd1a867734a2ed9ca2
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490826"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>PowerShell cmdlet을 사용하여 구성 및 관리 Microsoft Defender 바이러스 백신

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

PowerShell을 사용하여 여러 기능을 수행할 수 Windows Defender. 명령 프롬프트 또는 명령줄과 마찬가지로 PowerShell은 특히 시스템 관리용으로 설계된 작업 기반 명령줄 셸 및 스크립팅 언어입니다. 자세한 내용은 [MSDN의 PowerShell 허브에서 읽어 볼 수 있습니다.](/previous-versions/msdn10/mt173057(v=msdn.10))

cmdlet 및 해당 기능 및 사용 가능한 매개 변수 목록은 [Defender cmdlets 항목을 참조하세요.](/powershell/module/defender)

PowerShell cmdlet은 GUI(그래픽 Windows 인터페이스)를 사용하여 소프트웨어를 구성하지 않는 서버 환경에서 가장 유용합니다.

> [!NOTE]
> PowerShell cmdlet은 Microsoft Endpoint Configuration Manager, 그룹 정책 관리 콘솔 또는 그룹 [](/configmgr)정책 [ADMX](https://www.microsoft.com/download/101445)템플릿과 같은 Microsoft Defender 바이러스 백신 대체로 사용하면 안 됩니다. [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

PowerShell을 사용하여 변경한 내용은 변경 내용이 배포되거나 적용된 끝점의 로컬 설정에 영향을 미치게 됩니다. 즉, 그룹 정책, 정책 Microsoft Endpoint Configuration Manager 또는 Microsoft Intune PowerShell을 사용하여 변경한 내용을 덮어 사용할 수 있습니다.

로컬 정책 다시 설정으로 로컬로 다시 정할 수 있는 설정을 [구성할 수 있습니다.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

PowerShell은 일반적으로 폴더 아래에 `%SystemRoot%\system32\WindowsPowerShell` 설치됩니다.

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>PowerShell cmdlet Microsoft Defender 바이러스 백신 사용

1. 검색 Windows **powershell 을 입력합니다.**
2. **결과에서** Windows PowerShell 를 선택하여 인터페이스를 열 수 있습니다.
3. PowerShell 명령과 매개 변수를 입력합니다.

> [!NOTE]
> 관리자 모드에서 PowerShell을 열 필요가 있을 수 있습니다. 관리자 권한에서 항목을 시작 메뉴 관리자 권한으로  실행을 클릭하고 사용 권한 프롬프트에서 **예를** 클릭합니다.

cmdlet에 대한 온라인 도움말을 열기 위해 다음을 입력합니다.

```PowerShell
Get-Help <cmdlet> -Online
```

로컬로 `-online` 캐시된 도움말을 얻기 위해 매개 변수를 생략합니다.

## <a name="related-topics"></a>관련 항목

- [관리 및 구성 도구에 대한 참조 항목](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 바이러스 백신 Cmdlet](/powershell/module/defender)