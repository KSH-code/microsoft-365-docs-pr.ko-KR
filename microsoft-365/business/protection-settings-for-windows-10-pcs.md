---
title: Windows 10 PC에서 장치 보호 설정 설정하기
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 기본 및 Windows 10 장치 보호 하기 위해 Microsoft 365 비즈니스에서 사용할 수 있는 기타 설정 하는 방법에 대 한 설명 합니다.
ms.openlocfilehash: ebfe5f59e544b67e5a4f2ecd990031e9221ff8e5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869715"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="3eeb1-103">Windows 10 PC에서 장치 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="3eeb1-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="3eeb1-104">Windows 10 장치 보안</span><span class="sxs-lookup"><span data-stu-id="3eeb1-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="3eeb1-105">Microsoft 365 Business를 사용하여 Windows 10 장치를 안전하게 보호하는 방법에 대한 비디오를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="3eeb1-106">전역 관리자 자격 증명을 사용하여 [Microsoft 365 Business](https://portal.office.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-106">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="3eeb1-107">관리 센터의 **장치 정책** 카드에서 **정책 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-107">in the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="3eeb1-109">**정책 추가** 창에서 이 정책의 고유 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="3eeb1-110">**정책 유형**에서 **Windows 10 장치 구성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-110">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="3eeb1-p101">확장 **Windows 10 장치 보안을 유지** 하 고 \> 하려는 방식 설정을 구성 합니다. 자세한 내용은 [사용할 수 있는 설정](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="3eeb1-113">언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-113">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="3eeb1-p102">다음 결정 **가 이러한 설정을 받아볼?** 이러한 설정은 받아볼 수 있는 보안 그룹에 대 한 기본 **모든 사용자에 게** 보안 그룹 선택 **변경**를 사용 하 여 않으려면 검색 \> **을 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="3eeb1-117">마지막으로 **완료**를 선택하여 정책을 저장하고 장치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="3eeb1-118">사용 가능한 설정</span><span class="sxs-lookup"><span data-stu-id="3eeb1-118">Available settings</span></span>

<span data-ttu-id="3eeb1-p103">모든 설정의 기본값은 **켬**입니다. 다음과 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="3eeb1-121">자세한 내용은 [Microsoft 365 Business의 보호 기능을 Intune 설정에 매핑하는 방법](map-protection-features-to-intune-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-121">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3eeb1-122">설정</span><span class="sxs-lookup"><span data-stu-id="3eeb1-122">Setting</span></span>  <br/> |<span data-ttu-id="3eeb1-123">설명</span><span class="sxs-lookup"><span data-stu-id="3eeb1-123">Description</span></span>  <br/> |
|<span data-ttu-id="3eeb1-124">Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="3eeb1-124">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="3eeb1-125">인터넷에 연결하여 발생할 수 있는 위험으로부터 PC를 보호하기 위해 Windows Defender Antivirus가 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-125">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="3eeb1-126">Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원</span><span class="sxs-lookup"><span data-stu-id="3eeb1-126">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="3eeb1-127">Edge에서 사용자를 악성 사이트와 다운로드로부터 보호하는 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-127">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="3eeb1-128">장치의 공격 표면을 줄이는 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="3eeb1-128">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="3eeb1-p104">'켬'으로 설정하면 공격 표면이 감소하여 일반적으로 맬웨어가 장치를 감염시키는 데 사용되는 작업 및 앱을 차단할 수 있습니다. 이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다. 자세한 내용은 [공격 표면 축소](https://go.microsoft.com/fwlink/?linkid=870417)를 참조하세요.  </span><span class="sxs-lookup"><span data-stu-id="3eeb1-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="3eeb1-132">랜섬웨어와 같은 위협으로부터 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="3eeb1-132">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="3eeb1-p105">이 설정은 제어된 폴더 액세스를 사용하여 랜섬웨어와 같은 의심스러운 앱이나 악성 앱에 의해 회사 데이터가 수정되는 것을 방지합니다. 이러한 유형의 앱은 보호된 폴더를 변경할 수 없도록 차단됩니다. 이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다. 자세한 내용은 [제어된 폴더 액세스를 사용하여 폴더 보호](https://go.microsoft.com/fwlink/?linkid=870418)를 참조하세요.  </span><span class="sxs-lookup"><span data-stu-id="3eeb1-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="3eeb1-137">인터넷의 의심스러운 콘텐츠에 대한 네트워크 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="3eeb1-137">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="3eeb1-p106">피싱 메일, 익스플로잇 또는 기타 악의적 콘텐츠를 호스트할 수 있는 평판이 낮은 인터넷 위치에 대한 아웃바운드 사용자 연결을 차단하려면 이 설정을 사용합니다. 이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다. 자세한 내용은 [네트워크 보호](https://go.microsoft.com/fwlink/?linkid=870419)를 참조하세요.  </span><span class="sxs-lookup"><span data-stu-id="3eeb1-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="3eeb1-141">BitLocker를 사용하여 PC의 파일 및 폴더를 무단 액세스로부터 보호</span><span class="sxs-lookup"><span data-stu-id="3eeb1-141">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="3eeb1-p107">Bitlocker는 컴퓨터 하드 드라이브를 암호화하여 데이터를 보호하고, 컴퓨터가 분실되거나 도난당한 경우 데이터 노출을 방지합니다. 자세한 내용은 [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000)를 참조하세요.  </span><span class="sxs-lookup"><span data-stu-id="3eeb1-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="3eeb1-144">사용자가 Microsoft Store에서 앱을 다운로드할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3eeb1-144">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="3eeb1-p108">사용자가 Microsoft Store에서 앱을 다운로드하여 설치할 수 있도록 허용합니다. 앱에는 게임에서 생산성 도구에 이르기까지 다양한 종류가 있습니다. 따라서 기본값은 **켜기**이지만 관리자가 보안을 위해 끌 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="3eeb1-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="3eeb1-147">사용자가 Cortana에 액세스할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3eeb1-147">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="3eeb1-p109">Cortana는 매우 유용한 도구입니다. Cortana는 사용자 대신 설정을 끄거나 켜고, 길을 안내해 주고, 약속을 상기시켜 줍니다. 기본값은 **켜기**입니다.  </span><span class="sxs-lookup"><span data-stu-id="3eeb1-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="3eeb1-150">사용자가 Microsoft에서 Windows 팁 및 광고를 받을 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3eeb1-150">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="3eeb1-151">Windows 팁은 새로운 기능이 출시된 경우 사용자에게 이를 안내하는 등 매우 유용하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-151">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="3eeb1-152">자동으로 Windows 10 장치를 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="3eeb1-152">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="3eeb1-153">Windows 10 장치가 자동으로 최신 상태로 업데이트되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-153">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="3eeb1-154">이 시간 동안 유휴 상태일 때 장치 화면 끄기</span><span class="sxs-lookup"><span data-stu-id="3eeb1-154">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="3eeb1-p110">사용자가 유휴 상태일 때 회사 데이터가 안전하게 보호되도록 합니다. 사용자가 커피숍과 같은 공공장소에서 작업하다가 잠시 자리를 비우거나 다른 곳에 주의를 기울인 순간 장치가 타인의 시선에 노출될 수 있습니다. 이 설정은 사용자가 얼마 동안 유휴 상태이면 화면이 꺼지는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3eeb1-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

