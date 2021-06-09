---
title: PC에 대한 장치 보호 Windows 10 편집하거나 만들기
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 비즈니스용 장치에서 사용할 수 있는 설정에 대해 Microsoft 365 장치를 보호하는 Windows 10 대해 자세히 알아보아야 합니다.
ms.openlocfilehash: acfb27b2e4592d4ed1e446a63c9495ae07d916de
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578230"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="b1112-103">PC에 대한 장치 보호 Windows 10 편집하거나 만들기</span><span class="sxs-lookup"><span data-stu-id="b1112-103">Edit or create device protection settings for Windows 10 PCs</span></span>

<span data-ttu-id="b1112-104">이 문서는 이 문서에 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b1112-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="b1112-105">설치 페이지에서 기본 Windows 보호 설정을 지정한 후 모든 사용자 또는 사용자 집합에 적용되는 새 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-105">After you have set set up default Windows protection settings on the Setup page, you can add new ones that apply to either all users, or a set of users.</span></span> <span data-ttu-id="b1112-106">만든 파일을 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-106">You can also edit any of the ones you have created.</span></span>

## <a name="create-protection-settings-for-windows-10-devices"></a><span data-ttu-id="b1112-107">장치용 보호 Windows 10 만들기</span><span class="sxs-lookup"><span data-stu-id="b1112-107">Create protection settings for Windows 10 devices</span></span>

<span data-ttu-id="b1112-108">다음을 통해 디바이스를 보호하는 Windows 10 비디오를 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b1112-108">View a video on how to secure Windows 10 devices with Microsoft 365 Business Premium:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="b1112-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="b1112-110">왼쪽 nav에서 장치 정책 **추가** \> **를** \> **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b1112-110">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="b1112-111">**정책 추가** 창에서 이 정책의 고유 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-111">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="b1112-112">**정책 유형** 에서 **Windows 10 장치 구성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-112">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
5. <span data-ttu-id="b1112-113">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="b1112-113">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="b1112-114">자세한 내용은 사용 가능한 설정을 [참조하세요.](#available-settings)</span><span class="sxs-lookup"><span data-stu-id="b1112-114">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="b1112-115">언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-115">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="b1112-p103">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="b1112-p103">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
7. <span data-ttu-id="b1112-119">마지막으로 **완료** 를 선택하여 정책을 저장하고 장치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-119">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 

## <a name="edit-windows-10-protection-settings"></a><span data-ttu-id="b1112-120">보호 Windows 10 편집</span><span class="sxs-lookup"><span data-stu-id="b1112-120">Edit Windows 10 protection settings</span></span>
 
1. <span data-ttu-id="b1112-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-121">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="b1112-122">왼쪽 nav에서 장치 **정책을** \> **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b1112-122">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="b1112-123">기존 Windows 장치 정책을 선택한 다음 편집 **을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b1112-123">Choose an existing Windows device policy and then **Edit**.</span></span>
1. <span data-ttu-id="b1112-124">변경하려는 설정 옆에 있는 편집을 선택한 다음 저장 을 **선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="b1112-124">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="available-settings"></a><span data-ttu-id="b1112-125">사용 가능한 설정</span><span class="sxs-lookup"><span data-stu-id="b1112-125">Available settings</span></span>

<span data-ttu-id="b1112-p104">모든 설정의 기본값은 **켬** 입니다. 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-p104">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="b1112-128">자세한 내용은 [Intune 설정에](map-protection-features-to-intune-settings.md)매핑되는 Microsoft 365 Premium 기능을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1112-128">For more information, see [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b1112-129">설정</span><span class="sxs-lookup"><span data-stu-id="b1112-129">Setting</span></span>  <br/> |<span data-ttu-id="b1112-130">설명</span><span class="sxs-lookup"><span data-stu-id="b1112-130">Description</span></span>  <br/> |
|<span data-ttu-id="b1112-131">Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="b1112-131">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="b1112-132">인터넷에 연결하여 발생할 수 있는 위험으로부터 PC를 보호하기 위해 Windows Defender Antivirus가 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-132">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="b1112-133">Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="b1112-133">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="b1112-134">Edge에서 사용자를 악성 사이트와 다운로드로부터 보호하는 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-134">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="b1112-135">장치의 공격 표면을 줄이는 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="b1112-135">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="b1112-p105">'켬'으로 설정하면 공격 표면이 감소하여 일반적으로 맬웨어가 장치를 감염시키는 데 사용되는 작업 및 앱을 차단할 수 있습니다. 이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다. 자세한 내용은 [공격 표면 축소](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)를 참조하세요.  </span><span class="sxs-lookup"><span data-stu-id="b1112-p105">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) to learn more.  </span></span><br/> |
|<span data-ttu-id="b1112-139">랜섬웨어와 같은 위협으로부터 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="b1112-139">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="b1112-140">이 설정은 제어된 폴더 액세스를 사용하여 랜섬웨어와 같은 의심스러운 앱이나 악성 앱에 의해 회사 데이터가 수정되는 것을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-140">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware.</span></span> <span data-ttu-id="b1112-141">이러한 유형의 앱은 보호된 폴더를 변경할 수 없도록 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-141">These types of apps are blocked from making changes in protected folders.</span></span> <span data-ttu-id="b1112-142">이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-142">This setting is only available if Windows Defender Antivirus is set to On.</span></span> <span data-ttu-id="b1112-143">자세한 [내용은 제어된](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) 폴더 액세스로 폴더 보호를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-143">See [Protect folders with Controlled folder access](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) to learn more.</span></span>  <br/> |
|<span data-ttu-id="b1112-144">인터넷의 의심스러운 콘텐츠에 대한 네트워크 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="b1112-144">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="b1112-145">피싱 사기, 악용 또는 기타 악의적인 콘텐츠를 호스팅할 수 있는 신뢰도 낮은 인터넷 위치에 대한 아웃바운드 사용자 연결을 차단하려면 이 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-145">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits, or other malicious content.</span></span> <span data-ttu-id="b1112-146">이 설정은 으로 설정된 Windows Defender 바이러스 백신 사용할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b1112-146">This setting is only available if Windows Defender Antivirus is set to **On**.</span></span> <span data-ttu-id="b1112-147">자세한 내용은 네트워크 [보호를 참조하세요.](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="b1112-147">For more information, see [Protect your network](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).</span></span>  <br/> |
|<span data-ttu-id="b1112-148">BitLocker를 사용하여 PC의 파일 및 폴더를 무단 액세스로부터 보호</span><span class="sxs-lookup"><span data-stu-id="b1112-148">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="b1112-149">Bitlocker는 컴퓨터 하드 드라이브를 암호화하여 데이터를 보호하고, 컴퓨터가 분실되거나 도난당한 경우 데이터 노출을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-149">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="b1112-150">자세한 내용은 [Bitlocker FAQ 를 참조하세요.](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)</span><span class="sxs-lookup"><span data-stu-id="b1112-150">For more information, see [Bitlocker FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).</span></span>  <br/> |
|<span data-ttu-id="b1112-151">사용자가 Microsoft Store에서 앱을 다운로드할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="b1112-151">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="b1112-p109">사용자가 Microsoft Store에서 앱을 다운로드하여 설치할 수 있도록 허용합니다. 앱에는 게임에서 생산성 도구에 이르기까지 다양한 종류가 있습니다. 따라서 기본값은 **켜기** 이지만 관리자가 보안을 위해 끌 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="b1112-p109">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="b1112-154">사용자가 Cortana에 액세스할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="b1112-154">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="b1112-155">Cortana가 매우 유용할 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="b1112-155">Cortana can be very helpful!</span></span> <span data-ttu-id="b1112-156">Cortana는 설정을 켜거나 끄고, 길안내를 제공하며, 약속이 준비되어 있는지 확인하여 이 설정을 기본적으로 **켜기로** 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-156">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="b1112-157">사용자가 Microsoft에서 Windows 팁 및 광고를 받을 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="b1112-157">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="b1112-158">Windows 팁은 새로운 기능이 출시된 경우 사용자에게 이를 안내하는 등 매우 유용하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-158">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="b1112-159">자동으로 Windows 10 장치를 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="b1112-159">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="b1112-160">Windows 10 장치가 자동으로 최신 상태로 업데이트되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-160">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="b1112-161">이 시간 동안 유휴 상태일 때 장치 화면 끄기</span><span class="sxs-lookup"><span data-stu-id="b1112-161">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="b1112-p111">사용자가 유휴 상태일 때 회사 데이터가 안전하게 보호되도록 합니다. 사용자가 커피숍과 같은 공공장소에서 작업하다가 잠시 자리를 비우거나 다른 곳에 주의를 기울인 순간 장치가 타인들의 시선에 노출될 수 있습니다. 이 설정은 사용자가 얼마 동안 유휴 상태이면 화면이 꺼지는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1112-p111">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |