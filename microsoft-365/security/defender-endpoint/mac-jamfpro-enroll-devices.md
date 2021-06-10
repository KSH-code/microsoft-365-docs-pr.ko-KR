---
title: MacOS 장치에서 Endpoint용 Microsoft Defender를 Jamf 2013에 Pro
description: MacOS 장치에서 Endpoint용 Microsoft Defender를 Jamf 2013에 Pro
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, 제거, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 0fa0db3ba85ff003d91b43d06c709ab66c37ce02
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933100"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a><span data-ttu-id="571d8-104">MacOS 장치에서 Endpoint용 Microsoft Defender를 Jamf 2013에 Pro</span><span class="sxs-lookup"><span data-stu-id="571d8-104">Enroll Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="571d8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="571d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="571d8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="571d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="571d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="571d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="571d8-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="571d8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="571d8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="571d8-110">macOS 장치 등록</span><span class="sxs-lookup"><span data-stu-id="571d8-110">Enroll macOS devices</span></span>

<span data-ttu-id="571d8-111">JamF에 등록하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="571d8-112">이 문서에서는 다음 두 가지 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="571d8-113">방법 1: 등록 초대</span><span class="sxs-lookup"><span data-stu-id="571d8-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="571d8-114">방법 2: 사전 등록</span><span class="sxs-lookup"><span data-stu-id="571d8-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="571d8-115">전체 목록은 컴퓨터 등록 [정보를 참조하세요.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)</span><span class="sxs-lookup"><span data-stu-id="571d8-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="571d8-116">등록 방법 1: 등록 초대</span><span class="sxs-lookup"><span data-stu-id="571d8-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="571d8-117">Jamf Pro 대시보드에서 등록 **초대로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="571d8-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![구성 설정의 이미지1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="571d8-119">**+ 새로 고치기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="571d8-119">Select **+ New**.</span></span>

    ![자동으로 생성된 로고 설명 클로즈업](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="571d8-121">전자 **메일 주소에서** 초대 > 받는  사람 지정에 받는 사람의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![구성 설정의 이미지2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![구성 설정의 이미지3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="571d8-124">예: janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="571d8-124">For example: janedoe@contoso.com</span></span>

    ![구성 설정의 이미지4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="571d8-126">초대에 대한 메시지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-126">Configure the message for the invitation.</span></span>

    ![구성 설정의 이미지5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![구성 설정의 이미지6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![구성 설정의 이미지7](images/3ced5383a6be788486d89d407d042f28.png)

    ![구성 설정의 이미지8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="571d8-131">등록 방법 2: 사전 등록</span><span class="sxs-lookup"><span data-stu-id="571d8-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="571d8-132">Jamf Pro 대시보드에서 **사전 등록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="571d8-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![구성 설정의 이미지9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="571d8-134">컴퓨터 사전 [등록의 지침을 따릅니다.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)</span><span class="sxs-lookup"><span data-stu-id="571d8-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="571d8-135">macOS 장치 등록</span><span class="sxs-lookup"><span data-stu-id="571d8-135">Enroll macOS device</span></span>

1. <span data-ttu-id="571d8-136">**계속을** 선택하고 시스템 기본 설정 창에서 CA **인증서를 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="571d8-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Jamf Pro 등록 이미지1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="571d8-138">CA 인증서가 설치되면 브라우저 창으로 돌아가 **계속을** 선택하고 MDM 프로필을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Jamf Pro 등록 이미지2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="571d8-140">**JAMF에서** 다운로드 허용을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Jamf Pro 등록 이미지3](images/jamfpro-download.png)

4. <span data-ttu-id="571d8-142">**계속을** 선택하여 MDM 프로필 설치를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Jamf Pro 등록의 이미지](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="571d8-144">**계속을** 선택하여 MDM 프로필을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Jamf Pro 등록5의 이미지](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="571d8-146">**계속을** 선택하여 구성을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="571d8-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Jamf Pro 등록6의 이미지](images/jamfpro-mdm-profile.png)
