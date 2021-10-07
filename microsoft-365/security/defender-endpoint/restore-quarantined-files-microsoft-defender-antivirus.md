---
title: Microsoft Defender 바이러스 백신에서 격리된 파일 복원
description: 2016년 8월 1일부로 전송된 파일 및 폴더를 복원할 Microsoft Defender 바이러스 백신.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/23/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 0eed4f8b615ce759cd81385546158232d51c6158
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168209"
---
# <a name="restore-quarantined-files-in-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신에서 격리된 파일 복원

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

장치에서 Microsoft Defender 바이러스 백신 감지하고 수정하도록 구성된 경우 의심스러운 파일을 Microsoft Defender 바이러스 백신 수 있습니다. 분리된 파일이 위협이 아닌 경우 복원할 수 있습니다.

1. 를 **Windows 보안.**
2. 바이러스 **& 보호를 선택한** 다음 보호 기록 **을 클릭합니다.**
3. 모든 최근 항목 목록에서 **Quarantined Items(Quarantined Items)를 필터링합니다.**
4. 유지할 항목을 선택하고 복원과 같은 작업을 실행합니다.

> [!TIP]
> 명령 프롬프트를 사용하여 파일을 검지에서 복원할 수도 있습니다. 자세한 [내용은 Restore a file from quarantine 을 참조합니다.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine) 

## <a name="related-articles"></a>관련 문서

- [검사에 대한 수정 구성](configure-remediation-microsoft-defender-antivirus.md)
- [검사 결과 검토](review-scan-results-microsoft-defender-antivirus.md)
- [파일 이름, 확장명 및 폴더 위치를 기반으로 제외 구성 및 유효성 검사](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 서버에서 Windows 제외 구성](configure-server-exclusions-microsoft-defender-antivirus.md)