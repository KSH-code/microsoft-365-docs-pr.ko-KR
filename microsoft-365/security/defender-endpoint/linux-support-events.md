---
title: Linux에서 끝점용 Microsoft Defender에 대한 누락된 이벤트 또는 경고 문제 해결
description: Linux의 끝점용 Microsoft Defender에서 누락된 이벤트 또는 경고 문제를 해결합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 이벤트
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7de216c1397a7cc4806af8221257eeedd2290830
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933316"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="05f00-104">Linux에서 끝점용 Microsoft Defender에 대한 누락된 이벤트 또는 경고 문제 해결</span><span class="sxs-lookup"><span data-stu-id="05f00-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="05f00-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="05f00-105">**Applies to:**</span></span>

- [<span data-ttu-id="05f00-106">Microsoft Defender for Endpoint(Linux용)</span><span class="sxs-lookup"><span data-stu-id="05f00-106">Microsoft Defender for Endpoint on Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="05f00-107">이 문서에서는 보안 센터 포털에서 누락된 이벤트 또는 알림을 완화하는 몇 가지 일반적인 [단계를](https://securitycenter.windows.com/) 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="05f00-108">**끝점용 Microsoft Defender가** 장치에 올바르게 설치되면  포털에 장치 페이지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="05f00-109">디바이스 페이지의 시간 표시 막대 탭 또는 고급 헌팅 페이지에서 기록된 모든 이벤트를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="05f00-110">이 섹션에서는 일부 또는 모든 예상 이벤트가 누락된 경우를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="05f00-111">예를 들어 _모든 CreatedFile_ 이벤트가 누락된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="05f00-112">네트워크 및 로그인 이벤트 누락</span><span class="sxs-lookup"><span data-stu-id="05f00-112">Missing network and login events</span></span>

<span data-ttu-id="05f00-113">끝점용 Microsoft Defender는 linux의 프레임워크를 활용하여 네트워크 및 로그인 `audit` 활동을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="05f00-114">감사 프레임워크가 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="05f00-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="05f00-115">예상 출력:</span><span class="sxs-lookup"><span data-stu-id="05f00-115">expected output:</span></span>

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. <span data-ttu-id="05f00-116">`auditd`중지됨으로 표시된 경우 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="05f00-117">**SLES 시스템에서** SYSCALL 감사는 기본적으로 사용하지 않도록 설정되어 있으며 누락된 이벤트를 `auditd` 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="05f00-118">SYSCALL 감사가 사용하지 않도록 설정되어 있지 않은지 확인을 위해 현재 감사 규칙을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="05f00-119">다음 줄이 있는 경우 해당 줄을 제거하거나 편집하여 끝점용 Microsoft Defender가 특정 SYSCAL을 추적할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="05f00-120">감사 규칙은 에 `/etc/audit/rules.d/audit.rules` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="05f00-121">파일 이벤트 누락</span><span class="sxs-lookup"><span data-stu-id="05f00-121">Missing file events</span></span>

<span data-ttu-id="05f00-122">파일 이벤트는 프레임워크를 통해 `fanotify` 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="05f00-123">일부 또는 모든 파일 이벤트가 누락되는 경우 장치에서 사용하도록 설정되어 있으며 파일 시스템이 `fanotify` 지원되는지 [확인합니다.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="05f00-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="05f00-124">컴퓨터의 파일 시스템 목록을 다음으로 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="05f00-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
