---
title: Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사
description: Microsoft Defender 바이러스 백신 클라우드 보호 서비스에 대한 연결을 구성하고 테스트합니다.
keywords: 바이러스 백신, Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 클라우드, 적극성, 보호 수준
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 6ccc2eb171e85793899a7862ed9a317815d89626
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007587"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="452aa-104">Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="452aa-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

<span data-ttu-id="452aa-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="452aa-105">**Applies to:**</span></span>

- [<span data-ttu-id="452aa-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="452aa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="452aa-107">Microsoft Defender 바이러스 백신 클라우드 제공 보호가 제대로 작동하려면 보안 팀이 끝점과 특정 Microsoft 서버 간의 연결을 허용하도록 네트워크를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, your security team must configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="452aa-108">이 문서에서는 방화벽 규칙을 사용하는 등 허용해야 하는 연결을 나열하고 연결 유효성을 검사하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="452aa-109">보호를 올바르게 구성하면 클라우드 제공 보호 서비스에서 최고의 가치를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="452aa-110">네트워크 연결에 대한 자세한 내용은 블로그 게시물 [Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 끝점에 대한 중요한 변경 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="452aa-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="452aa-111">Microsoft Defender for Endpoint 데모 웹 [사이트를](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com 다음 기능이 작동하고 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="452aa-111">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="452aa-112">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="452aa-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="452aa-113">빠른 학습(차단 시 차단 포함)</span><span class="sxs-lookup"><span data-stu-id="452aa-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="452aa-114">잠재적으로 원치 않는 응용 프로그램 차단</span><span class="sxs-lookup"><span data-stu-id="452aa-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="452aa-115">Microsoft Defender 바이러스 백신 클라우드 서비스에 대한 연결 허용</span><span class="sxs-lookup"><span data-stu-id="452aa-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="452aa-116">Microsoft Defender 바이러스 백신 클라우드 서비스는 끝점을 빠르고 강력하게 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="452aa-117">클라우드 제공 보호 서비스를 사용하도록 설정하는 것은 선택 사항이지만 끝점 및 네트워크 전체에서 맬웨어에 대한 중요한 보호 기능을 제공하기 때문에 이 서비스를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span> <span data-ttu-id="452aa-118">Intune, Microsoft Endpoint Configuration Manager, 그룹 정책, PowerShell cmdlet 또는 Windows 보안 앱의 개별 클라이언트에서 서비스를 사용하도록 설정하는 데 대한 자세한 내용은 클라우드 제공 보호 사용을 참조하세요. [](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="452aa-118">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="452aa-119">서비스를 사용하도록 설정한 후 네트워크 또는 방화벽과 끝점 간의 연결을 허용하도록 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-119">After you've enabled the service, you might need to configure your network or firewall to allow connections between it and your endpoints.</span></span> <span data-ttu-id="452aa-120">보호는 클라우드 서비스이기 때문에 컴퓨터는 인터넷에 액세스할 수 있어야 합니다. Microsoft Defender for Office 365 기계 학습 서비스에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-120">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="452aa-121">모든 종류의 네트워크 검사에서 URL을 `*.blob.core.windows.net` 제외하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-121">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

> [!NOTE]
> <span data-ttu-id="452aa-122">Microsoft Defender 바이러스 백신 클라우드 서비스는 네트워크 및 끝점에 업데이트된 보호를 제공하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-122">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="452aa-123">클라우드 서비스라고 하지만 단순히 클라우드에 저장된 파일을 보호하는 것이 아니라 분산 리소스와 기계 학습을 사용하여 기존 보안 인텔리전스 업데이트보다 훨씬 빠른 속도로 끝점에 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-123">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

## <a name="services-and-urls"></a><span data-ttu-id="452aa-124">서비스 및 URL</span><span class="sxs-lookup"><span data-stu-id="452aa-124">Services and URLs</span></span>

<span data-ttu-id="452aa-125">이 섹션의 표에는 서비스 및 해당 연결된 웹 사이트 주소(URL)가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-125">The table in this section lists the services and their associated website addresses (URLs).</span></span> 

<span data-ttu-id="452aa-126">이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-126">Make sure that there are no firewall or network filtering rules denying access to these URLs.</span></span> <span data-ttu-id="452aa-127">그렇지 않으면 URL을 제외한 해당 규칙에 대해 특별히 허용 규칙을 만들어야 할 수 `*.blob.core.windows.net` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-127">Otherwise, you might need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="452aa-128">다음 표의 URL은 통신에 포트 443을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-128">The URLs in the following table use port 443 for communication.</span></span>

| <span data-ttu-id="452aa-129">서비스 및 설명</span><span class="sxs-lookup"><span data-stu-id="452aa-129">Service and description</span></span> | <span data-ttu-id="452aa-130">URL</span><span class="sxs-lookup"><span data-stu-id="452aa-130">URL</span></span> |
|----|---- |
| <span data-ttu-id="452aa-131">MICROSOFT Defender 바이러스 백신 클라우드 제공 보호 서비스(MAPS(Microsoft Active Protection Service)라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-131">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span><p><span data-ttu-id="452aa-132">이 서비스는 Microsoft Defender 바이러스 백신에서 클라우드 제공 보호를 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-132">This service is used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| <span data-ttu-id="452aa-133">MICROSOFT 업데이트 서비스(MU) 및 WU(Windows 업데이트 서비스)</span><span class="sxs-lookup"><span data-stu-id="452aa-133">Microsoft Update Service (MU) and Windows Update Service (WU)</span></span> <p><span data-ttu-id="452aa-134">이러한 서비스를 통해 보안 인텔리전스 및 제품 업데이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-134">These services allow for security intelligence and product updates</span></span>   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> <span data-ttu-id="452aa-135">자세한 내용은 Windows 업데이트용 [연결 끝점을 참조합니다.](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="452aa-135">For more details, see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="452aa-136">보안 인텔리전스 업데이트 ADL(대체 다운로드 위치)</span><span class="sxs-lookup"><span data-stu-id="452aa-136">Security intelligence updates Alternate Download Location (ADL)</span></span><p><span data-ttu-id="452aa-137">설치된 보안 인텔리전스가 최신 상태로 유지된 경우(7일 이상 후) Microsoft Defender 바이러스 백신 보안 인텔리전스 업데이트의 대체 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-137">This is an alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="452aa-138">맬웨어 제출 저장소</span><span class="sxs-lookup"><span data-stu-id="452aa-138">Malware submission storage</span></span> <p><span data-ttu-id="452aa-139">제출 양식 또는 자동 샘플 제출을 통해 Microsoft에 제출된 파일의 업로드 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-139">This is the upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span> | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="452aa-140">CRL(인증서 해지 목록)</span><span class="sxs-lookup"><span data-stu-id="452aa-140">Certificate Revocation List (CRL)</span></span> <p><span data-ttu-id="452aa-141">이 목록은 CRL을 업데이트하기 위해 MAPS에 대한 SSL 연결을 만들 때 Windows에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-141">This list is used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="452aa-142">기호 저장소</span><span class="sxs-lookup"><span data-stu-id="452aa-142">Symbol Store</span></span> <p><span data-ttu-id="452aa-143">기호 저장소는 Microsoft Defender 바이러스 백신에서 수정 흐름 중에 중요한 특정 파일을 복원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-143">The symbol store is used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>   | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="452aa-144">유니버설 원격 분석 클라이언트</span><span class="sxs-lookup"><span data-stu-id="452aa-144">Universal Telemetry Client</span></span> <p><span data-ttu-id="452aa-145">이 클라이언트는 Windows에서 클라이언트 진단 데이터를 전송하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-145">This client is used by Windows to send client diagnostic data</span></span><p> <span data-ttu-id="452aa-146">Microsoft Defender 바이러스 백신은 제품 품질 모니터링을 위해 원격 분석 사용</span><span class="sxs-lookup"><span data-stu-id="452aa-146">Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>    | <span data-ttu-id="452aa-147">이 업데이트는 SSL(TCP 포트 443)을 사용하여 매니페스트를 다운로드하고 다음 DNS 끝점을 사용하는 진단 데이터를 Microsoft에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-147">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:</span></span> <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="452aa-148">네트워크와 클라우드 간의 연결 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="452aa-148">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="452aa-149">위에 나열된 URL을 허용한 후 Microsoft Defender 바이러스 백신 클라우드 서비스에 연결되어 있으며 완전히 보호되도록 정보를 올바르게 보고하고 받는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-149">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a><span data-ttu-id="452aa-150">cmdline 도구를 사용하여 클라우드 제공 보호 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="452aa-150">Use the cmdline tool to validate cloud-delivered protection</span></span>

<span data-ttu-id="452aa-151">Microsoft Defender 바이러스 백신 명령줄 유틸리티()와 함께 다음 인수를 사용하여 네트워크가 Microsoft Defender 바이러스 백신 클라우드 서비스와 통신할 수 있는지 `mpcmdrun.exe` 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-151">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="452aa-152">명령 프롬프트의 관리자 수준 버전을 열 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-152">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="452aa-153">시작 메뉴에서 항목을 마우스 오른쪽  단추로 클릭하고 관리자 권한으로 실행을 클릭한 다음 사용 권한 프롬프트에서 **예를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-153">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="452aa-154">이 명령은 Windows 10 버전 1703 이상에서만 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-154">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="452aa-155">자세한 내용은 명령줄 도구를 사용하여 Microsoft Defender 바이러스 mpcmdrun.exe [관리를 참조하세요.](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="452aa-155">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a><span data-ttu-id="452aa-156">Microsoft에서 가짜 맬웨어 파일을 다운로드하려고 시도</span><span class="sxs-lookup"><span data-stu-id="452aa-156">Attempt to download a fake malware file from Microsoft</span></span>

<span data-ttu-id="452aa-157">클라우드에 제대로 연결되어 있는 경우 Microsoft Defender 바이러스 백신에서 검색하고 차단하는 샘플 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-157">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="452aa-158">를 방문하여 파일을 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-158">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="452aa-159">이 파일은 실제 맬웨어 조각이 아니기 때문에</span><span class="sxs-lookup"><span data-stu-id="452aa-159">This file is not an actual piece of malware.</span></span> <span data-ttu-id="452aa-160">클라우드에 제대로 연결되어 있는지 테스트하도록 설계된 위조 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-160">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="452aa-161">제대로 연결된 경우 Microsoft Defender 바이러스 백신 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-161">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="452aa-162">Microsoft Edge를 사용하는 경우 알림 메시지도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-162">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Edge에서 맬웨어가 발견된 알림 스크린샷":::

<span data-ttu-id="452aa-164">다음을 사용하는 경우 유사한 메시지가 Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="452aa-164">A similar message occurs if you're using Internet Explorer:</span></span>

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="맬웨어가 발견된 Microsoft Defender AV 알림":::

<span data-ttu-id="452aa-166">또한 Windows 보안 앱의 검사 기록 섹션에서  **Quarantined threats** 아래에 검색이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-166">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="452aa-167">작업 표시줄에서 방패 아이콘을 클릭하거나 보안에 대한 시작 메뉴를 검색하여 Windows 보안 앱을 열 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="452aa-167">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="452aa-168">바이러스 **& 보호를 선택한** 다음 보호 기록 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="452aa-168">Select **Virus & threat protection**, and then select **Protection history**.</span></span>

3. <span data-ttu-id="452aa-169">**Quarantined threats(Quarantined threats)** 섹션에서 **전체** 기록 보기를 선택하여 검색된 가짜 맬웨어를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="452aa-170">버전 1703 이전의 Windows 10 버전에는 다른 사용자 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452aa-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="452aa-171">[Windows 보안 앱에서 Microsoft Defender 바이러스 백신을 참조하세요.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="452aa-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="452aa-172">Windows 이벤트 로그에는 클라이언트 [Windows Defender ID 1116도 표시됩니다.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="452aa-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

