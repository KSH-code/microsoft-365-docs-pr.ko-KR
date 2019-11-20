---
title: Windows 10 PC에서 장치 보호 설정 설정하기
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Microsoft 365 Business에서 사용할 수 있는 기본 및 기타 설정에 대해 설명 하 고 Windows 10 장치를 보호 합니다.
ms.openlocfilehash: 1846ee7ae09db94575ef27dcf4f5721661f7666d
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715205"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="7bdf4-103">Windows 10 PC에서 장치 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="7bdf4-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="7bdf4-104">Windows 10 장치 보안</span><span class="sxs-lookup"><span data-stu-id="7bdf4-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="7bdf4-105">Microsoft 365 Business를 사용하여 Windows 10 장치를 안전하게 보호하는 방법에 대한 비디오를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="7bdf4-106"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="7bdf4-107">왼쪽 탐색 창에서 **장치** \> **정책** \> **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="7bdf4-108">**정책 추가** 창에서 이 정책의 고유 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="7bdf4-109">**정책 유형**에서 **Windows 10 장치 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="7bdf4-110">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-110">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="7bdf4-111">자세한 내용은 [사용 가능한 설정을](#available-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-111">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="7bdf4-112">언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-112">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="7bdf4-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="7bdf4-116">마지막으로 **완료**를 선택하여 정책을 저장하고 장치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="7bdf4-117">사용 가능한 설정</span><span class="sxs-lookup"><span data-stu-id="7bdf4-117">Available settings</span></span>

<span data-ttu-id="7bdf4-118">모든 설정의 기본값은 **켬**입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-118">By default all settings are **On**.</span></span> <span data-ttu-id="7bdf4-119">다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-119">The following settings are available.</span></span>
  
<span data-ttu-id="7bdf4-120">자세한 내용은 [Microsoft 365 Business의 보호 기능을 Intune 설정에 매핑하는 방법](map-protection-features-to-intune-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-120">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7bdf4-121">설정</span><span class="sxs-lookup"><span data-stu-id="7bdf4-121">Setting</span></span>  <br/> |<span data-ttu-id="7bdf4-122">설명</span><span class="sxs-lookup"><span data-stu-id="7bdf4-122">Description</span></span>  <br/> |
|<span data-ttu-id="7bdf4-123">Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="7bdf4-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="7bdf4-124">인터넷에 연결하여 발생할 수 있는 위험으로부터 PC를 보호하기 위해 Windows Defender Antivirus가 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="7bdf4-125">Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="7bdf4-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="7bdf4-126">Edge에서 사용자를 악성 사이트와 다운로드로부터 보호하는 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="7bdf4-127">장치의 공격 표면을 줄이는 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="7bdf4-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="7bdf4-p104">'켬'으로 설정하면 공격 표면이 감소하여 일반적으로 맬웨어가 장치를 감염시키는 데 사용되는 작업 및 앱을 차단할 수 있습니다. 이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다. 자세한 내용은 [공격 표면 축소](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)를 참조하세요.  </span><span class="sxs-lookup"><span data-stu-id="7bdf4-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) to learn more.  </span></span><br/> |
|<span data-ttu-id="7bdf4-131">랜섬웨어와 같은 위협으로부터 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="7bdf4-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="7bdf4-132">이 설정은 제어된 폴더 액세스를 사용하여 랜섬웨어와 같은 의심스러운 앱이나 악성 앱에 의해 회사 데이터가 수정되는 것을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-132">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware.</span></span> <span data-ttu-id="7bdf4-133">이러한 유형의 앱은 보호된 폴더를 변경할 수 없도록 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-133">These types of apps are blocked from making changes in protected folders.</span></span> <span data-ttu-id="7bdf4-134">이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-134">This setting is only available if Windows Defender Antivirus is set to On.</span></span> <span data-ttu-id="7bdf4-135">자세한 내용은 [제어 된 폴더 액세스 권한을 가진 폴더 보호](https://docs.microsoft.com/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-135">See [Protect folders with Controlled folder access](https://docs.microsoft.com/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) to learn more.</span></span>  <br/> |
|<span data-ttu-id="7bdf4-136">인터넷의 의심스러운 콘텐츠에 대한 네트워크 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="7bdf4-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="7bdf4-137">피싱 사기, 악용 또는 기타 악의적인 콘텐츠를 호스트할 수 있는 낮은 신뢰도의 인터넷 위치에 대 한 아웃 바운드 사용자 연결을 차단 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-137">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits, or other malicious content.</span></span> <span data-ttu-id="7bdf4-138">이 설정은 Windows Defender 바이러스 백신이 On으로 설정 되어 있는 경우 **에**만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-138">This setting is only available if Windows Defender Antivirus is set to **On**.</span></span> <span data-ttu-id="7bdf4-139">자세한 내용은 [네트워크 보호](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-139">For more information, see [Protect your network](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).</span></span>  <br/> |
|<span data-ttu-id="7bdf4-140">BitLocker를 사용하여 PC의 파일 및 폴더를 무단 액세스로부터 보호</span><span class="sxs-lookup"><span data-stu-id="7bdf4-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="7bdf4-141">Bitlocker는 컴퓨터 하드 드라이브를 암호화하여 데이터를 보호하고, 컴퓨터가 분실되거나 도난당한 경우 데이터 노출을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-141">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="7bdf4-142">자세한 내용은 [BITLOCKER FAQ](https://go.microsoft.com/fwlink/?linkid=871000)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-142">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="7bdf4-143">사용자가 Microsoft Store에서 앱을 다운로드할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="7bdf4-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="7bdf4-p108">사용자가 Microsoft Store에서 앱을 다운로드하여 설치할 수 있도록 허용합니다. 앱에는 게임에서 생산성 도구에 이르기까지 다양한 종류가 있습니다. 따라서 기본값은 **켜기**이지만 관리자가 보안을 위해 끌 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="7bdf4-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="7bdf4-146">사용자가 Cortana에 액세스할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="7bdf4-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="7bdf4-147">Cortana가 매우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-147">Cortana can be very helpful!</span></span> <span data-ttu-id="7bdf4-148">Cortana는 사용자에 대 한 설정을 설정 또는 해제 하 고, 약속 시간이 되었는지 확인 하 고,이 설정을 **기본적으로 유지** 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-148">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="7bdf4-149">사용자가 Microsoft에서 Windows 팁 및 광고를 받을 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="7bdf4-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="7bdf4-150">Windows 팁은 새로운 기능이 출시된 경우 사용자에게 이를 안내하는 등 매우 유용하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="7bdf4-151">자동으로 Windows 10 장치를 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="7bdf4-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="7bdf4-152">Windows 10 장치가 자동으로 최신 상태로 업데이트되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="7bdf4-153">이 시간 동안 유휴 상태일 때 장치 화면 끄기</span><span class="sxs-lookup"><span data-stu-id="7bdf4-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="7bdf4-p110">사용자가 유휴 상태일 때 회사 데이터가 안전하게 보호되도록 합니다. 사용자가 커피숍과 같은 공공장소에서 작업하다가 잠시 자리를 비우거나 다른 곳에 주의를 기울인 순간 장치가 타인들의 시선에 노출될 수 있습니다. 이 설정은 사용자가 얼마 동안 유휴 상태이면 화면이 꺼지는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
