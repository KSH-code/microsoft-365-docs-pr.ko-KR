---
title: Windows 10 장치에서 응용 프로그램 보호 설정 설정하기
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Windows 10 장치에서 앱 관리 정책을 만들고 작업 파일을 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: 670184a2e81721fb5cc063e854822e9b271164d9
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074613"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="3569a-103">Windows 10 장치에서 응용 프로그램 보호 설정 설정하기</span><span class="sxs-lookup"><span data-stu-id="3569a-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="3569a-104">Windows 10용 앱 관리 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3569a-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="3569a-105">사용자들이 업무를 수행할 수 있는 개인 Windows 10 장치를 갖고 있는 경우, 해당 장치에서도 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="3569a-106">관리 센터 ()로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>합니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="3569a-107">왼쪽 탐색 창에서 **장치** \> **정책** \> **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="3569a-108">**정책 추가** 창에서 이 정책의 고유 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="3569a-109">**정책 유형**에서 **Windows 10용 응용 프로그램 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="3569a-110">**장치 유형에**서 **개인** 또는 **소유한 회사**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="3569a-111">**작업 파일 암호화**가 자동으로 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="3569a-112">사용자가 작업 파일을 개인 PC에 저장하지 않도록 하려면 **사용자가 회사 데이터를 개인 파일로 복사하는 것을 차단하고 회사 파일은 비즈니스용 OneDrive에 저장하도록 합니다.** 를 **켜기**로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="3569a-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="3569a-113">**Windows 장치에서 데이터 복구**를 확장하여 **켜기**로 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-113">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="3569a-p101">데이터 복구 에이전트 인증서의 위치를 찾기 전에 먼저 하나 만들어야 합니다. 지침은 [EFS(파일 시스템 암호화) DRA(데이터 복구 에이전트) 인증서 만들기 및 확인](https://go.microsoft.com/fwlink/p/?linkid=853700)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3569a-p101">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="3569a-p102">기본적으로 작업 파일은 장치에 저장되고 사용자 프로필과 연결된 비밀 키를 사용하여 암호화됩니다. 사용자만 파일을 열고 암호 해독할 수 있습니다. 그러나 장치를 분실하거나 사용자가 제거된 경우 파일이 암호화된 상태에 계속 머물러 있을 수 있습니다. 관리자가 DRA(데이터 복구 에이전트) 인증서를 사용하여 파일의 암호를 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-p102">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="3569a-p103">추가 도메인 또는 SharePoint Online 위치를 추가하여 나열된 모든 앱이 보호되는지 확인하려면 **Protect additional network and cloud locations**(추가 네트워크 및 클라우드 위치 보호)를 확장합니다. 필드에 2개 이상의 항목을 입력해야 하는 경우 항목 사이에 세미콜론(;)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3569a-p103">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="3569a-p104">다음으로 **이러한 설정을 적용할 대상은 누구입니까?** 를 설정하세요. **모든 사용자** 기본 보안 그룹을 사용하지 않으려는 경우 **변경**을 선택하고 이 설정을 적용할 보안 그룹 \> **선택**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="3569a-126">마지막으로 **추가**를 선택하여 정책을 저장하고 장치에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3569a-126">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 