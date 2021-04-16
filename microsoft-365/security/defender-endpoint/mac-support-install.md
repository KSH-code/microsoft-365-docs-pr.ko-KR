---
title: Mac용 끝점용 Microsoft Defender 설치 문제 해결
description: Mac용 끝점용 Microsoft Defender의 설치 문제를 해결합니다.
keywords: microsoft, defender, atp, mac, 설치
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d2ad3160c9f36a27dc98f44365433de5f8b26bb2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861434"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d622b-104">macOS의 끝점용 Microsoft Defender 설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d622b-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d622b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d622b-105">**Applies to:**</span></span>

- [<span data-ttu-id="d622b-106">Microsoft Defender for Endpoint(macOS용)</span><span class="sxs-lookup"><span data-stu-id="d622b-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="d622b-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d622b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d622b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d622b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d622b-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d622b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d622b-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="d622b-111">설치 실패</span><span class="sxs-lookup"><span data-stu-id="d622b-111">Installation failed</span></span>

<span data-ttu-id="d622b-112">수동 설치의 경우 설치 마법사의 요약 페이지에 "설치하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="d622b-113">설치 관리자에서 오류가 발생하여 설치가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="d622b-114">소프트웨어 제조업체에 문의하여 도움을 요청하세요."</span><span class="sxs-lookup"><span data-stu-id="d622b-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="d622b-115">MDM 배포의 경우 일반 설치 실패로도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="d622b-116">최종 사용자에게 정확한 오류가 표시되지는는 하지만 설치 진행률이 있는 로그 파일은 에 `/Library/Logs/Microsoft/mdatp/install.log` 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="d622b-117">각 설치 세션은 이 로그 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="d622b-118">마지막 설치 `sed` 세션만 출력하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-118">You can use `sed` to output the last installation session only:</span></span>

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

<span data-ttu-id="d622b-119">이 예제에서는 실제 이유에 를(를) `[ERROR]` 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="d622b-120">이러한 버전 간 다운그레이드가 지원되지 않는 경우 설치에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="d622b-121">MDATP 설치 로그가 누락되거나 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="d622b-122">드물지만 설치는 MDATP의 /Library/Logs/Microsoft/mdatp/install.log 파일에 추적을 남기지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="d622b-123">macOS 로그를 쿼리하여 설치가 발생했다는 사실과 가능한 오류를 분석할 수 있습니다(클라이언트 UI가 없는 경우 MDM 배포에 유용합니다).</span><span class="sxs-lookup"><span data-stu-id="d622b-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="d622b-124">많은 정보가 제공될 수 있도록 좁은 시간 창을 사용하여 쿼리를 실행하고 로깅 프로세스 이름을 사용하여 필터링하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d622b-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
