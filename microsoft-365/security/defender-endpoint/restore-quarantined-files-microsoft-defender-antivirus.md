---
title: Microsoft Defender AV에서 고지된 파일 복원
description: Microsoft Defender AV에서 분리된 파일 및 폴더를 복원할 수 있습니다.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: e0253c4ac7d92c91e3fda45681568d721645f2b0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275387"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a><span data-ttu-id="b7d14-103">Microsoft Defender AV에서 고지된 파일 복원</span><span class="sxs-lookup"><span data-stu-id="b7d14-103">Restore quarantined files in Microsoft Defender AV</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b7d14-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b7d14-104">**Applies to:**</span></span>

- [<span data-ttu-id="b7d14-105">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b7d14-105">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b7d14-106">장치에서 Microsoft Defender 바이러스 백신 감지하고 수정하도록 구성된 경우 의심스러운 파일을 Microsoft Defender 바이러스 백신 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7d14-106">If Microsoft Defender Antivirus is configured to detect and remediate threats on your device, Microsoft Defender Antivirus quarantines suspicious files.</span></span> <span data-ttu-id="b7d14-107">분리된 파일이 위협이 아닌 경우 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7d14-107">If you are certain a quarantined file is not a threat, you can restore it.</span></span>

1. <span data-ttu-id="b7d14-108">를 **Windows 보안.**</span><span class="sxs-lookup"><span data-stu-id="b7d14-108">Open **Windows Security**.</span></span>
2. <span data-ttu-id="b7d14-109">바이러스 **& 보호를 선택한** 다음 보호 기록 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7d14-109">Select **Virus & threat protection** and then click **Protection history**.</span></span>
3. <span data-ttu-id="b7d14-110">모든 최근 항목 목록에서 **Quarantined Items(Quarantined Items)를 필터링합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7d14-110">In the list of all recent items, filter on **Quarantined Items**.</span></span>
4. <span data-ttu-id="b7d14-111">유지할 항목을 선택하고 복원과 같은 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d14-111">Select an item you want to keep, and take an action, such as restore.</span></span>

> [!TIP]
> <span data-ttu-id="b7d14-112">명령 프롬프트를 사용하여 파일을 검지에서 복원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7d14-112">Restoring a file from quarantine can also be done using Command Prompt.</span></span> <span data-ttu-id="b7d14-113">자세한 [내용은 Restore a file from quarantine 을 참조합니다.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)</span><span class="sxs-lookup"><span data-stu-id="b7d14-113">See [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span></span> 

## <a name="related-articles"></a><span data-ttu-id="b7d14-114">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b7d14-114">Related articles</span></span>

- [<span data-ttu-id="b7d14-115">검사에 대한 수정 구성</span><span class="sxs-lookup"><span data-stu-id="b7d14-115">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b7d14-116">검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="b7d14-116">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b7d14-117">파일 이름, 확장명 및 폴더 위치를 기반으로 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="b7d14-117">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b7d14-118">프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="b7d14-118">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b7d14-119">Microsoft Defender 바이러스 백신 서버에서 Windows 제외 구성</span><span class="sxs-lookup"><span data-stu-id="b7d14-119">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)