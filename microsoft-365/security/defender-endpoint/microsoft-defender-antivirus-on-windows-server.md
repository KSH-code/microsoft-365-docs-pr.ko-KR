---
title: Windows Server의 Microsoft Defender 바이러스 백신
description: Windows Server 2016 및 Windows Server 2019에서 Microsoft Defender 바이러스 백신을 사용하도록 설정하고 구성하는 방법을 학습합니다.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50e6f9b16dbc633e75e86acdc54ac43580107ae3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893380"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="9d575-104">Windows Server의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="9d575-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9d575-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9d575-105">**Applies to:**</span></span>

- [<span data-ttu-id="9d575-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9d575-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9d575-107">Microsoft Defender 바이러스 백신은 다음 버전의 Windows Server에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="9d575-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="9d575-108">Windows Server 2019</span></span>
- <span data-ttu-id="9d575-109">Windows Server, 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="9d575-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="9d575-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="9d575-110">Windows Server 2016.</span></span> 

<span data-ttu-id="9d575-111">경우에 따라 Microsoft Defender 바이러스 백신을 *Endpoint Protection이라고 합니다.* 그러나 보호 엔진은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="9d575-112">기능, 구성 및 관리는 [Windows 10의 Microsoft Defender 바이러스](microsoft-defender-antivirus-in-windows-10.md)백신에서 거의 동일하기는 하지만 Windows Server에는 몇 가지 주요 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="9d575-113">Windows Server에서 [자동](configure-server-exclusions-microsoft-defender-antivirus.md) 제외는 정의된 서버 역할에 따라 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-113">In Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
- <span data-ttu-id="9d575-114">Windows Server에서 다른 바이러스 백신 제품을 실행하는 경우 Microsoft Defender 바이러스 백신이 자동으로 비활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-114">In Windows Server, Microsoft Defender Antivirus does not automatically disable itself if you are running another antivirus product.</span></span>

## <a name="the-process-at-a-glance"></a><span data-ttu-id="9d575-115">프로세스 살펴보기</span><span class="sxs-lookup"><span data-stu-id="9d575-115">The process at a glance</span></span>

<span data-ttu-id="9d575-116">서버 플랫폼에서 Microsoft Defender 바이러스 백신을 설정하고 실행하는 프로세스에는 다음과 같은 몇 가지 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-116">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="9d575-117">[인터페이스를 사용하도록 설정합니다.](#enable-the-user-interface-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="9d575-117">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="9d575-118">[Microsoft Defender 바이러스 백신을 설치합니다.](#install-microsoft-defender-antivirus-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="9d575-118">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="9d575-119">[Microsoft Defender 바이러스 백신이 실행되고 있는지 확인](#verify-microsoft-defender-antivirus-is-running)</span><span class="sxs-lookup"><span data-stu-id="9d575-119">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="9d575-120">[맬웨어 방지 보안 인텔리전스를 업데이트합니다.](#update-antimalware-security-intelligence)</span><span class="sxs-lookup"><span data-stu-id="9d575-120">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="9d575-121">(필요한 경우) [샘플 제출](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="9d575-121">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="9d575-122">(필요한 경우) [자동 제외를 구성합니다.](#configure-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="9d575-122">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="9d575-123">(필요한 경우만 해당) [Microsoft Defender 바이러스 백신을 수동 모드로 설정](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="9d575-123">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="9d575-124">Windows Server에서 사용자 인터페이스 사용</span><span class="sxs-lookup"><span data-stu-id="9d575-124">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="9d575-125">기본적으로 Microsoft Defender 바이러스 백신은 Windows Server에 설치 및 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-125">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="9d575-126">GUI(사용자 인터페이스)는 일부 SKUS에 기본적으로 설치되지만 PowerShell 또는 기타 방법을 사용하여 Microsoft Defender 바이러스 백신을 관리할 수 있기 때문에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-126">The user interface (GUI) is installed by default on some SKUs, but is not required because you can use PowerShell or other methods to manage Microsoft Defender Antivirus.</span></span> <span data-ttu-id="9d575-127">GUI가 서버에 설치되어 있지 않은 경우 역할 및  기능 추가 마법사 또는 PowerShell cmdlet을 사용하여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-127">If the GUI is not installed on your server, you can add it by using the **Add Roles and Features** wizard, or by using PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="9d575-128">역할 및 기능 추가 마법사를 사용하여 GUI 켜기</span><span class="sxs-lookup"><span data-stu-id="9d575-128">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="9d575-129">역할 및 기능 추가 마법사를 사용하여 [역할,](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)역할 서비스 및 기능 설치 및 역할 및 기능 추가 마법사 사용을 **참조합니다.**</span><span class="sxs-lookup"><span data-stu-id="9d575-129">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="9d575-130">마법사의 기능  단계로 들어오면 Windows Defender **에서** 마법사의 기능 Windows Defender **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9d575-130">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="9d575-131">Windows Server 2016에서 역할 및 기능 추가 **마법사는** 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-131">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![역할 및 기능 마법사에 대한 GUI를 보여 Windows Defender 옵션](images/server-add-gui.png)

   <span data-ttu-id="9d575-133">Windows Server 2019에서 역할 추가 및 **기능 마법사는 비슷합니다.**</span><span class="sxs-lookup"><span data-stu-id="9d575-133">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="9d575-134">PowerShell을 사용하여 GUI 켜기</span><span class="sxs-lookup"><span data-stu-id="9d575-134">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="9d575-135">다음 PowerShell cmdlet은 인터페이스를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-135">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="9d575-136">Windows Server에 Microsoft Defender 바이러스 백신 설치</span><span class="sxs-lookup"><span data-stu-id="9d575-136">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="9d575-137">역할 및 기능  추가 마법사 또는 PowerShell을 사용하여 Microsoft Defender 바이러스 백신을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-137">You can use either the **Add Roles and Features Wizard** or PowerShell to install Microsoft Defender Antivirus.</span></span>

### <a name="use-the-add-roles-and-features-wizard"></a><span data-ttu-id="9d575-138">역할 및 기능 추가 마법사 사용</span><span class="sxs-lookup"><span data-stu-id="9d575-138">Use the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="9d575-139">이 문서 [를 참조하고](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)역할 및 기능 추가 **마법사를 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="9d575-139">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="9d575-140">마법사의 기능  단계에 도착하면 Microsoft Defender 바이러스 백신 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-140">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="9d575-141">또한 선택 **옵션에 대한 WINDOWS DEFENDER** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-141">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="9d575-142">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="9d575-142">Use PowerShell</span></span>

<span data-ttu-id="9d575-143">PowerShell을 사용하여 Microsoft Defender 바이러스 백신을 설치하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-143">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="9d575-144">Microsoft Defender 바이러스 백신에 포함된 맬웨어 방지 엔진에 대한 이벤트 메시지는 [Microsoft Defender AV](troubleshoot-microsoft-defender-antivirus.md)이벤트 에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-144">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="9d575-145">Microsoft Defender 바이러스 백신이 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="9d575-145">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="9d575-146">서버에서 Microsoft Defender 바이러스 백신이 실행되고 있는지 확인하기 위해 다음 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-146">To verify that Microsoft Defender Antivirus is running on your server, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="9d575-147">방화벽 보호가 켜져 있는지 확인하기 위해 다음 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-147">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="9d575-148">PowerShell 대신 명령 프롬프트를 사용하여 Microsoft Defender 바이러스 백신이 실행되고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-148">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="9d575-149">이를 위해 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-149">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="9d575-150">이 `sc query` 명령은 Microsoft Defender 바이러스 백신 서비스에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-150">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="9d575-151">Microsoft Defender 바이러스 백신이 실행 중이면 `STATE` 값이 `RUNNING` 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-151">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="9d575-152">맬웨어 방지 보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="9d575-152">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="9d575-153">업데이트된 맬웨어 방지 보안 인텔리전스를 사용하려면 Windows 업데이트 서비스가 실행되고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-153">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="9d575-154">WSUS(Windows Server Update Services)와 같은 업데이트 관리 서비스를 사용하는 경우 Microsoft Defender 바이러스 백신 보안 인텔리전스에 대한 업데이트가 관리하는 컴퓨터에 대해 승인되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-154">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="9d575-155">기본적으로 Windows 업데이트는 Windows Server 2019 또는 Windows Server 2016에서 업데이트를 자동으로 다운로드하여 설치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-155">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="9d575-156">다음 방법 중 하나를 사용하여 이 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-156">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="9d575-157">메서드</span><span class="sxs-lookup"><span data-stu-id="9d575-157">Method</span></span>  |<span data-ttu-id="9d575-158">설명</span><span class="sxs-lookup"><span data-stu-id="9d575-158">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9d575-159">**제어판의 Windows** 업데이트</span><span class="sxs-lookup"><span data-stu-id="9d575-159">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="9d575-160">- **업데이트를 자동으로 설치하면** 보안 인텔리전스 업데이트를 포함하여 모든 Windows Defender 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-160">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="9d575-161">- **업데이트를 다운로드하지만** 설치할지 여부를 선택할 수 Windows Defender 보안 인텔리전스 업데이트를 자동으로 다운로드하고 설치할 수 있지만 다른 업데이트는 자동으로 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-161">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="9d575-162">**그룹 정책**</span><span class="sxs-lookup"><span data-stu-id="9d575-162">**Group Policy**</span></span>     | <span data-ttu-id="9d575-163">관리 **템플릿\Windows 구성 요소\Windows 업데이트\자동** 업데이트 구성 경로의 그룹 정책에서 사용할 수 있는 설정을 사용하여 Windows 업데이트를 설정하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-163">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="9d575-164">**AUOptions** 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="9d575-164">The **AUOptions** registry key</span></span>     |<span data-ttu-id="9d575-165">다음 두 값을 사용하면 Windows 업데이트에서 보안 인텔리전스 업데이트를 자동으로 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-165">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="9d575-166">- **4**  -  **자동으로 업데이트를 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="9d575-166">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="9d575-167">이 값을 설정하면 보안 인텔리전스 업데이트를 포함하여 모든 Windows Defender 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-167">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="9d575-168">- **3**  -  **업데이트를 다운로드하지만 설치할지 여부를 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9d575-168">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="9d575-169">이 값을 Windows Defender 보안 인텔리전스 업데이트를 자동으로 다운로드하여 설치할 수 있지만 다른 업데이트는 자동으로 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-169">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="9d575-170">맬웨어로부터 보호를 유지하려면 다음 서비스를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-170">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="9d575-171">Windows 오류 보고 서비스</span><span class="sxs-lookup"><span data-stu-id="9d575-171">Windows Error Reporting service</span></span>

- <span data-ttu-id="9d575-172">Windows 업데이트 서비스</span><span class="sxs-lookup"><span data-stu-id="9d575-172">Windows Update service</span></span>

<span data-ttu-id="9d575-173">다음 표에는 Microsoft Defender 바이러스 백신 및 종속 서비스에 대한 서비스가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-173">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="9d575-174">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="9d575-174">Service Name</span></span>|<span data-ttu-id="9d575-175">파일 위치</span><span class="sxs-lookup"><span data-stu-id="9d575-175">File Location</span></span>|<span data-ttu-id="9d575-176">설명</span><span class="sxs-lookup"><span data-stu-id="9d575-176">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="9d575-177">Windows Defender 서비스(WinDefend)</span><span class="sxs-lookup"><span data-stu-id="9d575-177">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="9d575-178">이 서비스는 Microsoft Defender 바이러스 백신 서비스로, 모든 시간을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-178">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="9d575-179">Wersvc(Windows 오류 보고 서비스)</span><span class="sxs-lookup"><span data-stu-id="9d575-179">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="9d575-180">이 서비스는 오류 보고서를 Microsoft로 다시 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-180">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="9d575-181">Windows Defender 방화벽(MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="9d575-181">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="9d575-182">방화벽 서비스를 사용하도록 Windows Defender 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-182">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="9d575-183">Windows 업데이트(Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="9d575-183">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="9d575-184">보안 인텔리전스 업데이트 및 맬웨어 방지 엔진 업데이트를 다운로드하려면 Windows 업데이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-184">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="9d575-185">샘플 제출</span><span class="sxs-lookup"><span data-stu-id="9d575-185">Submit samples</span></span>

<span data-ttu-id="9d575-186">샘플 제출을 통해 Microsoft는 잠재적으로 악성 소프트웨어의 샘플을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-186">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="9d575-187">Microsoft 연구원들은 이러한 샘플을 사용하여 의심스러운 활동을 분석하고 업데이트된 맬웨어 방지 보안 인텔리전스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-187">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="9d575-188">.exe 파일 및 .dll 파일과 같은 프로그램 실행 파일을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-188">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="9d575-189">Microsoft Word 문서 및 PDF 파일과 같은 개인 데이터가 포함된 파일은 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-189">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="9d575-190">파일 제출</span><span class="sxs-lookup"><span data-stu-id="9d575-190">Submit a file</span></span>

1. <span data-ttu-id="9d575-191">제출 [가이드를 검토합니다.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="9d575-191">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="9d575-192">샘플 [제출 포털 을 방문하여](https://www.microsoft.com/wdsi/filesubmission)파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-192">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="9d575-193">자동 샘플 제출 사용</span><span class="sxs-lookup"><span data-stu-id="9d575-193">Enable automatic sample submission</span></span>

<span data-ttu-id="9d575-194">자동 샘플 제출을 사용하도록 설정하려면 Windows PowerShell 콘솔을 시작하고 다음 설정 중 하나에 따라 **SubmitSamplesConsent** 값 데이터를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="9d575-194">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="9d575-195">설정</span><span class="sxs-lookup"><span data-stu-id="9d575-195">Setting</span></span>  |<span data-ttu-id="9d575-196">설명</span><span class="sxs-lookup"><span data-stu-id="9d575-196">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9d575-197">**0**  -  **항상 프롬프트**</span><span class="sxs-lookup"><span data-stu-id="9d575-197">**0** - **Always prompt**</span></span>     |<span data-ttu-id="9d575-198">Microsoft Defender 바이러스 백신 서비스는 필요한 모든 파일의 제출을 확인하라는 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-198">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="9d575-199">이 설정은 Microsoft Defender 바이러스 백신의 기본 설정이지만 GUI가 없는 Windows Server 2016 또는 2019 설치에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-199">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="9d575-200">**1**   -  **안전한 샘플 자동 보내기**</span><span class="sxs-lookup"><span data-stu-id="9d575-200">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="9d575-201">Microsoft Defender 바이러스 백신 서비스는 "안전"으로 표시된 모든 파일을 전송하고 나머지 파일을 묻는 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-201">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="9d575-202">**2**  -  **보내지 않는 경우**</span><span class="sxs-lookup"><span data-stu-id="9d575-202">**2** - **Never send**</span></span>      |<span data-ttu-id="9d575-203">Microsoft Defender 바이러스 백신 서비스는 메시지를 표시하지 않습니다. 또한 어떤 파일도 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-203">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="9d575-204">**3**  -  **모든 샘플 자동 보내기**</span><span class="sxs-lookup"><span data-stu-id="9d575-204">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="9d575-205">Microsoft Defender 바이러스 백신 서비스는 확인 메시지를 표시하지 않고 모든 파일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-205">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="9d575-206">자동 제외 구성</span><span class="sxs-lookup"><span data-stu-id="9d575-206">Configure automatic exclusions</span></span>

<span data-ttu-id="9d575-207">보안 및 성능을 보장하기 위해 Windows Server 2016 또는 2019에서 Microsoft Defender 바이러스 백신을 사용할 때 설치하는 역할 및 기능에 따라 특정 제외가 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-207">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="9d575-208">Windows Server에서 Microsoft Defender 바이러스 백신에서 제외 [구성을 참조합니다.](configure-server-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9d575-208">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="9d575-209">Microsoft Defender 바이러스 백신을 수동 모드로 설정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9d575-209">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="9d575-210">Microsoft가 아닌 바이러스 백신 제품을 기본 바이러스 백신 솔루션으로 사용하는 경우 Microsoft Defender 바이러스 백신을 수동 모드로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="9d575-210">If you are using a non-Microsoft antivirus product as your primary antivirus solution, set Microsoft Defender Antivirus to passive mode.</span></span>  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="9d575-211">레지스트리 키를 사용하여 Microsoft Defender 바이러스 백신을 수동 모드로 설정</span><span class="sxs-lookup"><span data-stu-id="9d575-211">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="9d575-212">Windows Server, 버전 1803 또는 Windows Server 2019를 사용하는 경우 다음 레지스트리 키를 설정하여 Microsoft Defender 바이러스 백신을 수동 모드로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-212">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="9d575-213">경로: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="9d575-213">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="9d575-214">이름: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="9d575-214">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="9d575-215">유형: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="9d575-215">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="9d575-216">값: `1`</span><span class="sxs-lookup"><span data-stu-id="9d575-216">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="9d575-217">역할 및 기능 제거 마법사를 사용하여 Microsoft Defender 바이러스 백신을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9d575-217">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="9d575-218">역할, 역할 서비스 또는 기능 설치 또는 제거 및 역할 및 기능 **제거 마법사 사용을 참조합니다.** [](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)</span><span class="sxs-lookup"><span data-stu-id="9d575-218">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="9d575-219">마법사의 **기능** 단계에 도착하면 기능 Windows Defender **선택을 취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="9d575-219">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="9d575-220">Windows Defender 기능  섹션에서 Windows Defender 선택을  취소하면 에 대한 인터페이스 옵션 GUI를 제거하라는 **메시지가 Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="9d575-220">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="9d575-221">Microsoft Defender 바이러스 백신은 사용자 인터페이스 없이 정상적으로 **실행되지만** 핵심 구성 기능의 기능을 사용하지 않도록 설정한 경우 사용자 인터페이스를 Windows Defender 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-221">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="9d575-222">PowerShell을 사용하여 Microsoft Defender 바이러스 백신 사용자 인터페이스 끄기</span><span class="sxs-lookup"><span data-stu-id="9d575-222">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="9d575-223">Microsoft Defender 바이러스 백신 GUI를 끄기 위해 다음 PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-223">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="9d575-224">Windows Server 2016을 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="9d575-224">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="9d575-225">Windows Server 2016 및 Microsoft에서 제공하거나 개발하지 않은 타사 맬웨어 방지/바이러스 백신 제품을 사용하는 경우 Microsoft Defender 바이러스 백신을 사용하지 않도록 설정/제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-225">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="9d575-226">Windows 보안 앱은 제거할 수 없지만 이러한 지침에 따라 인터페이스를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-226">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="9d575-227">다음 PowerShell cmdlet은 Windows Server 2016에서 Microsoft Defender 바이러스 백신을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9d575-227">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a><span data-ttu-id="9d575-228">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d575-228">See also</span></span>

- [<span data-ttu-id="9d575-229">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="9d575-229">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9d575-230">Microsoft Defender 바이러스 백신 호환성</span><span class="sxs-lookup"><span data-stu-id="9d575-230">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
