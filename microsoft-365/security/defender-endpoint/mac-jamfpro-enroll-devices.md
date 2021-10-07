---
title: MacOS 장치에서 Endpoint용 Microsoft Defender를 Jamf 2013에 Pro
description: MacOS 장치에서 Endpoint용 Microsoft Defender를 Jamf 2013에 Pro
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, 제거, intune, jamfpro, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: afe044e2f8cc495ce7f74bc482a99689af3e9482
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207838"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>MacOS 장치에서 Endpoint용 Microsoft Defender를 Jamf 2013에 Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>macOS 장치 등록

JamF에 등록하는 방법에는 여러 가지가 있습니다.

이 문서에서는 다음 두 가지 방법을 안내합니다.

- [방법 1: 등록 초대](#enrollment-method-1-enrollment-invitations)
- [방법 2: 사전 등록](#enrollment-method-2-prestage-enrollments)

전체 목록은 컴퓨터 등록 [정보를 참조하세요.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)

## <a name="enrollment-method-1-enrollment-invitations"></a>등록 방법 1: 등록 초대

1. Jamf Pro 대시보드에서 등록 **초대로 이동합니다.**

    ![구성 설정의 이미지1.](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. **+ 새로 고치기 를 선택합니다.**

    ![로고 닫기 설명이 자동으로 생성됩니다.](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. 전자 **메일 주소에서** 초대 > 받는  사람 지정에 받는 사람의 전자 메일 주소를 입력합니다.

    ![구성 설정의 이미지2.](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![구성 설정의 이미지3.](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    예: janedoe@contoso.com

    ![구성 설정의 이미지4.](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. 초대에 대한 메시지를 구성합니다.

    ![구성 설정의 이미지5.](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![구성 설정의 이미지6.](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![구성 설정의 이미지7.](images/3ced5383a6be788486d89d407d042f28.png)

    ![구성 설정의 이미지8.](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>등록 방법 2: 사전 등록

1. Jamf Pro 대시보드에서 **사전 등록으로 이동합니다.**

    ![구성 설정의 이미지9.](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. 컴퓨터 사전 [등록의 지침을 따릅니다.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)

## <a name="enroll-macos-device"></a>macOS 장치 등록

1. **계속을** 선택하고 시스템 기본 설정 창에서 CA **인증서를 설치합니다.**

    ![Jamf Pro 등록의 이미지1.](images/jamfpro-ca-certificate.png)

2. CA 인증서가 설치되면 브라우저 창으로 돌아가 **계속을** 선택하고 MDM 프로필을 설치합니다.

    ![Jamf Pro 등록 이미지2.](images/jamfpro-install-mdm-profile.png)

3. **JAMF에서** 다운로드 허용을 선택합니다.

    ![Jamf Pro 등록 이미지3.](images/jamfpro-download.png)

4. **계속을** 선택하여 MDM 프로필 설치를 진행합니다.

    ![Jamf Pro 등록4의 이미지입니다.](images/jamfpro-install-mdm.png)

5. **계속을** 선택하여 MDM 프로필을 설치합니다.

    ![Jamf Pro 등록5의 이미지입니다.](images/jamfpro-mdm-unverified.png)

6. **계속을** 선택하여 구성을 완료합니다.

    ![Jamf Pro 등록6의 이미지입니다.](images/jamfpro-mdm-profile.png)
