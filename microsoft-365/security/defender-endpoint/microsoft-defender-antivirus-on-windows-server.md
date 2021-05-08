---
title: Windows Server의 Microsoft Defender 바이러스 백신
description: Windows Server 2016 및 Windows Server 2019에서 Microsoft Defender 바이러스 백신을 사용하도록 설정하고 구성하는 방법을 학습합니다.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269495"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="b0f56-104">Windows Server의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="b0f56-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0f56-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b0f56-105">**Applies to:**</span></span>

- [<span data-ttu-id="b0f56-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b0f56-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b0f56-107">Microsoft Defender 바이러스 백신은 다음 버전의 Windows Server에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="b0f56-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b0f56-108">Windows Server 2019</span></span>
- <span data-ttu-id="b0f56-109">Windows Server, 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="b0f56-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="b0f56-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="b0f56-110">Windows Server 2016.</span></span> 

<span data-ttu-id="b0f56-111">경우에 따라 Microsoft Defender 바이러스 백신을 *Endpoint Protection이라고 합니다.* 그러나 보호 엔진은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="b0f56-112">기능, 구성 및 관리는 [Windows 10의 Microsoft Defender 바이러스](microsoft-defender-antivirus-in-windows-10.md)백신에서 거의 동일하기는 하지만 Windows Server에는 몇 가지 주요 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="b0f56-113">Windows Server에서는 [](configure-server-exclusions-microsoft-defender-antivirus.md) 정의된 서버 역할에 따라 자동 제외가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="b0f56-114">Windows Server에서 Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션을 실행 중인 경우 Microsoft Defender 바이러스 백신은 자동으로 수동 모드 또는 비활성화 모드로 전환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="b0f56-115">그러나 수동 또는 비활성화 모드로 Microsoft Defender 바이러스 백신을 수동으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="b0f56-116">Windows Server에서 Microsoft Defender 바이러스 백신 설정</span><span class="sxs-lookup"><span data-stu-id="b0f56-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="b0f56-117">서버 플랫폼에서 Microsoft Defender 바이러스 백신을 설정하고 실행하는 프로세스에는 다음과 같은 몇 가지 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="b0f56-118">[인터페이스를 사용하도록 설정합니다.](#enable-the-user-interface-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="b0f56-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="b0f56-119">[Microsoft Defender 바이러스 백신을 설치합니다.](#install-microsoft-defender-antivirus-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="b0f56-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="b0f56-120">[Microsoft Defender 바이러스 백신이 실행되고 있는지 확인](#verify-microsoft-defender-antivirus-is-running)</span><span class="sxs-lookup"><span data-stu-id="b0f56-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="b0f56-121">[맬웨어 방지 보안 인텔리전스를 업데이트합니다.](#update-antimalware-security-intelligence)</span><span class="sxs-lookup"><span data-stu-id="b0f56-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="b0f56-122">(필요한 경우) [샘플 제출](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="b0f56-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="b0f56-123">(필요한 경우) [자동 제외를 구성합니다.](#configure-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="b0f56-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="b0f56-124">(필요한 경우만 해당) [Microsoft Defender 바이러스 백신을 수동 모드로 설정](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="b0f56-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="b0f56-125">Windows Server에서 사용자 인터페이스 사용</span><span class="sxs-lookup"><span data-stu-id="b0f56-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="b0f56-126">기본적으로 Microsoft Defender 바이러스 백신은 Windows Server에 설치 및 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="b0f56-127">GUI(사용자 인터페이스)가 기본적으로 설치되지만 GUI가 필요하지 않은 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="b0f56-128">PowerShell, 그룹 정책 또는 기타 방법을 사용하여 Microsoft Defender 바이러스 백신을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="b0f56-129">GUI가 서버에 설치되어 있지 않은 경우 역할 및 기능 추가  마법사 또는 PowerShell cmdlet을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="b0f56-130">역할 및 기능 추가 마법사를 사용하여 GUI 켜기</span><span class="sxs-lookup"><span data-stu-id="b0f56-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="b0f56-131">역할 및 기능 추가 마법사를 사용하여 [역할,](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)역할 서비스 및 기능 설치 및 역할 및 기능 추가 마법사 사용을 **참조합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0f56-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="b0f56-132">마법사의 기능  단계로 들어오면 Windows Defender **에서** 마법사의 기능 Windows Defender **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0f56-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="b0f56-133">Windows Server 2016에서 역할 및 기능 추가 **마법사는** 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![역할 및 기능 마법사에 대한 GUI를 보여 Windows Defender 옵션](images/server-add-gui.png)

   <span data-ttu-id="b0f56-135">Windows Server 2019에서 역할 추가 및 **기능 마법사는 비슷합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0f56-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="b0f56-136">PowerShell을 사용하여 GUI 켜기</span><span class="sxs-lookup"><span data-stu-id="b0f56-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="b0f56-137">다음 PowerShell cmdlet은 인터페이스를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="b0f56-138">Windows Server에 Microsoft Defender 바이러스 백신 설치</span><span class="sxs-lookup"><span data-stu-id="b0f56-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="b0f56-139">Windows Server에 Microsoft Defender 바이러스 백신을 설치하거나 다시 설치해야 하는 경우  역할 및 기능 추가 마법사 또는 PowerShell을 사용하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="b0f56-140">역할 및 기능 추가 마법사를 사용하여 Microsoft Defender 바이러스 백신 설치</span><span class="sxs-lookup"><span data-stu-id="b0f56-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="b0f56-141">이 문서 [를 참조하고](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)역할 및 기능 추가 **마법사를 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="b0f56-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="b0f56-142">마법사의 기능  단계에 도착하면 Microsoft Defender 바이러스 백신 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="b0f56-143">또한 선택 **옵션에 대한 WINDOWS DEFENDER** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="b0f56-144">PowerShell을 사용하여 Microsoft Defender 바이러스 백신 설치</span><span class="sxs-lookup"><span data-stu-id="b0f56-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="b0f56-145">PowerShell을 사용하여 Microsoft Defender 바이러스 백신을 설치하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="b0f56-146">Microsoft Defender 바이러스 백신에 포함된 맬웨어 방지 엔진에 대한 이벤트 메시지는 [Microsoft Defender AV](troubleshoot-microsoft-defender-antivirus.md)이벤트 에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="b0f56-147">Microsoft Defender 바이러스 백신이 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="b0f56-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="b0f56-148">Microsoft Defender 바이러스 백신이 설치되면 다음 단계는 실행 중인지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="b0f56-149">Windows Server 끝점에서 다음 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="b0f56-150">방화벽 보호가 켜져 있는지 확인하기 위해 다음 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="b0f56-151">PowerShell 대신 명령 프롬프트를 사용하여 Microsoft Defender 바이러스 백신이 실행되고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="b0f56-152">이를 위해 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="b0f56-153">이 `sc query` 명령은 Microsoft Defender 바이러스 백신 서비스에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="b0f56-154">Microsoft Defender 바이러스 백신이 실행 중이면 `STATE` 값이 `RUNNING` 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="b0f56-155">맬웨어 방지 보안 인텔리전스 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0f56-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="b0f56-156">업데이트된 맬웨어 방지 보안 인텔리전스를 사용하려면 Windows 업데이트 서비스가 실행되고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="b0f56-157">WSUS(Windows Server Update Services)와 같은 업데이트 관리 서비스를 사용하는 경우 Microsoft Defender 바이러스 백신 보안 인텔리전스에 대한 업데이트가 관리하는 컴퓨터에 대해 승인되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="b0f56-158">기본적으로 Windows 업데이트는 Windows Server 2019 또는 Windows Server 2016에서 업데이트를 자동으로 다운로드하여 설치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="b0f56-159">다음 방법 중 하나를 사용하여 이 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="b0f56-160">메서드</span><span class="sxs-lookup"><span data-stu-id="b0f56-160">Method</span></span>  |<span data-ttu-id="b0f56-161">설명</span><span class="sxs-lookup"><span data-stu-id="b0f56-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b0f56-162">**제어판의 Windows** 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0f56-162">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="b0f56-163">- **업데이트를 자동으로 설치하면** 보안 인텔리전스 업데이트를 포함하여 모든 Windows Defender 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-163">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="b0f56-164">- **업데이트를 다운로드하지만** 설치할지 여부를 선택할 수 Windows Defender 보안 인텔리전스 업데이트를 자동으로 다운로드하고 설치할 수 있지만 다른 업데이트는 자동으로 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-164">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="b0f56-165">**그룹 정책**</span><span class="sxs-lookup"><span data-stu-id="b0f56-165">**Group Policy**</span></span>     | <span data-ttu-id="b0f56-166">관리 **템플릿\Windows 구성 요소\Windows 업데이트\자동** 업데이트 구성 경로의 그룹 정책에서 사용할 수 있는 설정을 사용하여 Windows 업데이트를 설정하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="b0f56-167">**AUOptions** 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="b0f56-167">The **AUOptions** registry key</span></span>     |<span data-ttu-id="b0f56-168">다음 두 값을 사용하면 Windows 업데이트에서 보안 인텔리전스 업데이트를 자동으로 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="b0f56-169">- **4**  -  **자동으로 업데이트를 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0f56-169">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="b0f56-170">이 값을 설정하면 보안 인텔리전스 업데이트를 포함하여 모든 Windows Defender 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="b0f56-171">- **3**  -  **업데이트를 다운로드하지만 설치할지 여부를 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b0f56-171">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="b0f56-172">이 값을 Windows Defender 보안 인텔리전스 업데이트를 자동으로 다운로드하여 설치할 수 있지만 다른 업데이트는 자동으로 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="b0f56-173">맬웨어로부터 보호를 유지하려면 다음 서비스를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="b0f56-174">Windows 오류 보고 서비스</span><span class="sxs-lookup"><span data-stu-id="b0f56-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="b0f56-175">Windows 업데이트 서비스</span><span class="sxs-lookup"><span data-stu-id="b0f56-175">Windows Update service</span></span>

<span data-ttu-id="b0f56-176">다음 표에는 Microsoft Defender 바이러스 백신 및 종속 서비스에 대한 서비스가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="b0f56-177">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="b0f56-177">Service Name</span></span>|<span data-ttu-id="b0f56-178">파일 위치</span><span class="sxs-lookup"><span data-stu-id="b0f56-178">File Location</span></span>|<span data-ttu-id="b0f56-179">설명</span><span class="sxs-lookup"><span data-stu-id="b0f56-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="b0f56-180">Windows Defender 서비스(WinDefend)</span><span class="sxs-lookup"><span data-stu-id="b0f56-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="b0f56-181">이 서비스는 Microsoft Defender 바이러스 백신 서비스로, 모든 시간을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="b0f56-182">Wersvc(Windows 오류 보고 서비스)</span><span class="sxs-lookup"><span data-stu-id="b0f56-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="b0f56-183">이 서비스는 오류 보고서를 Microsoft로 다시 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="b0f56-184">Windows Defender 방화벽(MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="b0f56-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="b0f56-185">방화벽 서비스를 사용하도록 Windows Defender 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="b0f56-186">Windows 업데이트(Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="b0f56-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="b0f56-187">보안 인텔리전스 업데이트 및 맬웨어 방지 엔진 업데이트를 다운로드하려면 Windows 업데이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="b0f56-188">샘플 제출</span><span class="sxs-lookup"><span data-stu-id="b0f56-188">Submit samples</span></span>

<span data-ttu-id="b0f56-189">샘플 제출을 통해 Microsoft는 잠재적으로 악성 소프트웨어의 샘플을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="b0f56-190">Microsoft 연구원들은 이러한 샘플을 사용하여 의심스러운 활동을 분석하고 업데이트된 맬웨어 방지 보안 인텔리전스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="b0f56-191">파일 및 파일 파일과 같은 .exe 실행 파일을 .dll 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="b0f56-192">Microsoft Word 문서 및 PDF 파일과 같은 개인 데이터가 포함된 파일은 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="b0f56-193">파일 제출</span><span class="sxs-lookup"><span data-stu-id="b0f56-193">Submit a file</span></span>

1. <span data-ttu-id="b0f56-194">제출 [가이드를 검토합니다.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="b0f56-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="b0f56-195">샘플 [제출 포털 을 방문하여](https://www.microsoft.com/wdsi/filesubmission)파일을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="b0f56-196">자동 샘플 제출 사용</span><span class="sxs-lookup"><span data-stu-id="b0f56-196">Enable automatic sample submission</span></span>

<span data-ttu-id="b0f56-197">자동 샘플 제출을 사용하도록 설정하려면 Windows PowerShell 콘솔을 시작하고 다음 설정 중 하나에 따라 **SubmitSamplesConsent** 값 데이터를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0f56-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="b0f56-198">설정</span><span class="sxs-lookup"><span data-stu-id="b0f56-198">Setting</span></span>  |<span data-ttu-id="b0f56-199">설명</span><span class="sxs-lookup"><span data-stu-id="b0f56-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b0f56-200">**0**  -  **항상 프롬프트**</span><span class="sxs-lookup"><span data-stu-id="b0f56-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="b0f56-201">Microsoft Defender 바이러스 백신 서비스는 필요한 모든 파일의 제출을 확인하라는 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="b0f56-202">이 설정은 Microsoft Defender 바이러스 백신의 기본 설정이지만 GUI가 없는 Windows Server 2016 또는 2019 설치에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="b0f56-203">**1**   -  **안전한 샘플 자동 보내기**</span><span class="sxs-lookup"><span data-stu-id="b0f56-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="b0f56-204">Microsoft Defender 바이러스 백신 서비스는 "안전"으로 표시된 모든 파일을 전송하고 나머지 파일을 묻는 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="b0f56-205">**2**  -  **보내지 않는 경우**</span><span class="sxs-lookup"><span data-stu-id="b0f56-205">**2** - **Never send**</span></span>      |<span data-ttu-id="b0f56-206">Microsoft Defender 바이러스 백신 서비스는 메시지를 표시하지 않습니다. 또한 어떤 파일도 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="b0f56-207">**3**  -  **모든 샘플 자동 보내기**</span><span class="sxs-lookup"><span data-stu-id="b0f56-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="b0f56-208">Microsoft Defender 바이러스 백신 서비스는 확인 메시지를 표시하지 않고 모든 파일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="b0f56-209">자동 제외 구성</span><span class="sxs-lookup"><span data-stu-id="b0f56-209">Configure automatic exclusions</span></span>

<span data-ttu-id="b0f56-210">보안 및 성능을 보장하기 위해 Windows Server 2016 또는 2019에서 Microsoft Defender 바이러스 백신을 사용할 때 설치하는 역할 및 기능에 따라 특정 제외가 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="b0f56-211">Windows Server에서 Microsoft Defender 바이러스 백신에서 제외 [구성을 참조합니다.](configure-server-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b0f56-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="b0f56-212">Microsoft Defender 바이러스 백신을 수동 모드로 설정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="b0f56-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="b0f56-213">Windows Server에서 Microsoft가 아닌 바이러스 백신 제품을 기본 바이러스 백신 솔루션으로 사용하는 경우 Microsoft Defender 바이러스 백신을 수동 모드 또는 비활성화 모드로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="b0f56-214">Windows Server, 버전 1803 이상 또는 Windows Server 2019에서 Microsoft Defender 바이러스 백신을 수동 모드로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="b0f56-215">Windows Server 2016에서 Microsoft Defender 바이러스 백신은 비 Microsoft 바이러스 백신/맬웨어 방지 제품과 함께 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="b0f56-216">이러한 경우 Microsoft Defender 바이러스 백신을 비활성화 모드로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a><span data-ttu-id="b0f56-217">PowerShell을 사용하여 Microsoft Defender 바이러스 백신을 수동 모드로 설정</span><span class="sxs-lookup"><span data-stu-id="b0f56-217">Set Microsoft Defender Antivirus to passive mode using PowerShell</span></span>

<span data-ttu-id="b0f56-218">Windows Server, 버전 1803 또는 Windows Server 2019를 사용하는 경우 다음 PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신을 수동 모드로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by using the following PowerShell cmdlet:</span></span>

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a><span data-ttu-id="b0f56-219">그룹 정책을 사용하여 Microsoft Defender 바이러스 백신을 수동 모드로 설정</span><span class="sxs-lookup"><span data-stu-id="b0f56-219">Set Microsoft Defender Antivirus to passive mode using Group Policy</span></span>

<span data-ttu-id="b0f56-220">필요한 절차</span><span class="sxs-lookup"><span data-stu-id="b0f56-220">PROCEDURE NEEDED</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="b0f56-221">레지스트리 키를 사용하여 Microsoft Defender 바이러스 백신을 수동 모드로 설정</span><span class="sxs-lookup"><span data-stu-id="b0f56-221">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="b0f56-222">Windows Server, 버전 1803 또는 Windows Server 2019를 사용하는 경우 다음 레지스트리 키를 설정하여 Microsoft Defender 바이러스 백신을 수동 모드로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-222">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="b0f56-223">경로: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="b0f56-223">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="b0f56-224">이름: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="b0f56-224">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="b0f56-225">유형: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="b0f56-225">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="b0f56-226">값: `1`</span><span class="sxs-lookup"><span data-stu-id="b0f56-226">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="b0f56-227">역할 및 기능 제거 마법사를 사용하여 Microsoft Defender 바이러스 백신을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="b0f56-227">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="b0f56-228">역할, 역할 서비스 또는 기능 설치 또는 제거 및 역할 및 기능 **제거 마법사 사용을 참조합니다.** [](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)</span><span class="sxs-lookup"><span data-stu-id="b0f56-228">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="b0f56-229">마법사의 **기능** 단계에 도착하면 기능 Windows Defender **선택을 취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0f56-229">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="b0f56-230">Windows Defender 기능  섹션에서 Windows Defender 선택을  취소하면 에 대한 인터페이스 옵션 GUI를 제거하라는 **메시지가 Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="b0f56-230">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="b0f56-231">Microsoft Defender 바이러스 백신은 사용자 인터페이스 없이 정상적으로 **실행되지만** 핵심 구성 기능의 기능을 사용하지 않도록 설정한 경우 사용자 인터페이스를 Windows Defender 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-231">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="b0f56-232">PowerShell을 사용하여 Microsoft Defender 바이러스 백신 사용자 인터페이스 끄기</span><span class="sxs-lookup"><span data-stu-id="b0f56-232">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="b0f56-233">Microsoft Defender 바이러스 백신 GUI를 끄기 위해 다음 PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-233">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="b0f56-234">Windows Server 2016을 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="b0f56-234">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="b0f56-235">Windows Server 2016 및 Microsoft에서 제공하거나 개발하지 않은 타사 맬웨어 방지/바이러스 백신 제품을 사용하는 경우 Microsoft Defender 바이러스 백신을 사용하지 않도록 설정/제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-235">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="b0f56-236">Windows 보안 앱은 제거할 수 없지만 이러한 지침에 따라 인터페이스를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-236">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="b0f56-237">다음 PowerShell cmdlet은 Windows Server 2016에서 Microsoft Defender 바이러스 백신을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-237">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="b0f56-238">Windows Server 2016에서 Microsoft Defender 바이러스 백신을 사용하지 않도록 설정하기 위해 다음 PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0f56-238">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="b0f56-239">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0f56-239">See also</span></span>

- [<span data-ttu-id="b0f56-240">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="b0f56-240">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="b0f56-241">Microsoft Defender 바이러스 백신 호환성</span><span class="sxs-lookup"><span data-stu-id="b0f56-241">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
