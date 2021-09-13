---
title: 장치 이미지
description: 새 디바이스를 주문하거나 기존 장치를 다시 사용할 때의 이미지 요구 사항
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fb3646e2ff339115d3fe6043ed45ea8f2140105a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215365"
---
# <a name="device-images"></a>장치 이미지


새 [디바이스를](#new-devices) 주문하거나 [](#existing-devices) 기존 장치를 재사용하는 경우 디바이스의 이미지가 장치 요구 사항을 충족하는지 보장하는 몇 가지 [옵션이 있습니다.](device-requirements.md#check-hardware-requirements)

## <a name="new-devices"></a>새 장치
승인된 제조업체에서 새 [](device-requirements.md#minimum-requirements)장치를 주문할 때 다음 단계에 따라 올바른 이미지 및 소프트웨어 구성으로 장치를 Microsoft Managed Desktop 확인합니다. 서비스에 특정 장치 모델을 처음 등록할 계획이면 언제든지 예제를 테스트하여 원하는 사용자 환경을 제공할 수 있도록 해야 합니다. 자세한 내용은 새 장치 [유효성 검사를 참조하세요.](/microsoft-365/managed-desktop/get-started/validate-device)

### <a name="dell"></a>Dell
Dell 영업 담당자와 직접 작업합니다. 이 담당자가 승인한 이미지가 Microsoft Managed Desktop 장치에 적용해야 합니다. Dell 장치, 이미지 및 주문 프로세스에 대한 자세한 내용은 에 문의 MMD_at_dell@dell.com.

### <a name="hp"></a>HP 
HP에서 새 장치를 주문하는 경우 쇼핑 Windows 10 Pro 비즈니스 장치 사이트에 있는 각 모델에 [](https://www.microsoft.com/windowsforbusiness/view-all-devices#view-all-filter) 대한 추가 요구 사항 섹션에 나열된 특정 SKU를 사용하세요(보기를 필터링하여 Microsoft Managed Desktop 장치 표시).

예외로 승인되어 있지만 현재 장치 목록 페이지에 나열되지 않은 장치를 HP에서 주문하는 경우 모델에 사용할 SKU를 요청해야 합니다. [](customizing.md) 예외 요청을 사용하여 HP와 함께 이 정보를 얻게 됩니다. 다음 주소를 사용하여 장치 및 장치 주문 지침에 대한 질문이 있으면 HP에 직접 문의할 수 있습니다.
 
- 미주: mmd-americas@hp.com
- 유럽/중동/아프리카: mmd-emea@hp.com
- 아시아 태평양/일본: mmd-apj@hp.com
- 전역: mmd@hp.com

### <a name="lenovo"></a>Lenovo
Lenovo에서 디바이스를 사용하여 Microsoft Managed Desktop 주문하는 경우 주문의 일부로 포함된 특정 부분 번호를 지정해야 합니다. Lenovo 영업 담당자 또는 Lenovo 채널 파트너에게 문의하여 장치 요구 사항을 충족하는 시스템을 사용하여 *"* 특수한 경매 모델"을 만들 것을 [요청합니다.](device-requirements.md#minimum-requirements) Microsoft Managed Desktop 호환되는 미리 로드된 이미지를 포함하려면 영업 담당자에게 "시스템 문서 블록 부분 번호 *SBB0Q94938 – MMD* 사용"을 참조하도록 요청합니다. 권장 서비스, 지원 및 이미징 서비스를 위해 Lenovo 영업 담당자 또는 Lenovo 채널 파트너와 협력하세요.

### <a name="microsoft"></a>Microsoft
장치 요구 사항을 충족하는 모든 Microsoft 디바이스에는 장치 요구 사항과 함께 작동하는 이미지가 Microsoft Managed Desktop. 다른 단계는 필요하지 않습니다.

Microsoft 디바이스의 공장에서 사용할 수 있는 최신 이미지를 얻습니다. Surface 전문가와 함께 Surface "Pegged PO" 프로세스를 사용합니다.

## <a name="existing-devices"></a>기존 장치

장치 요구 사항과 소프트웨어 요구 사항을 [](device-requirements.md#minimum-requirements) 모두 충족하는 한 기존 장치를 다시 [사용할 수 있습니다.](device-requirements.md#installed-software) 제조업체와 관련된 단계를 따릅니다.

제조업체의 이미지 또는 "유니버설 이미지"를 사용하여 디바이스의 이미지를 Microsoft Managed Desktop 수 있습니다. 적절한 제조업체 이미지를 얻기 위해 다시 [](#new-devices) 사용할 모델의 새 디바이스를 하나 이상 주문할 수 있습니다. 그런 다음 해당 장치에서 이미지를 얻은 후 정확히 동일한 모델의 다른 장치에 적용할 수 있습니다.

> [!NOTE]
> 이미지를 만들고 테스트하고 배포할 책임은 사용자에게 있습니다. 또한 가능한 경우 "유니버설 이미지"를 포함하여 사용자 지정 이미지 대신 제조업체에서 제공하는 적절한 이미지를 사용하는 것이 좋습니다.

### <a name="hp"></a>HP

HP 회사 준비 이미지와 함께 배송된 HP 상용 PC에는 를 포함합니다. 복구를 위한 WIM 파일입니다. 이 이미지를 사용하여 동일한 모델의 다른 장치에 공장 복원 이미지를 적용할 수 있습니다.

다음 단계에서는 디바이스의 모든 데이터를 제거하기 때문에 시작하기 전에 유지하려는 데이터를 백업해야 합니다.

1. [WinPE를 사용하여 부팅 가능한 USB](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) 드라이브를 만들 수 있습니다.
2. C: \\ SOURCES에서 USB 드라이브로 다음 파일을 복사합니다.
    - 공장 복구 WIM 파일(예: HP \_ EliteBook \_ 840 \_ G7 \_ 노트북 PC \_ \_ \_ CR 2004.wim)
    - 배포. CMD
    - ReCreatePartitions.txt
3. [WinPE로 디바이스 부팅](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB 드라이브.
4. 명령 프롬프트에서 를 [Diskpart.exe. ](/windows-server/administration/windows-commands/diskpart#additional-references)
5. Diskpart에서 를 실행한 다음 기본 저장소 디스크 `list disk` 번호(일반적으로 디스크 0)를 기록합니다.
6. 를 입력하여 Diskpart를 `exit` 종료합니다.
7. 명령 프롬프트에서 를 실행합니다. 여기서 sys_disk 는 방금 결정한 기본 저장소 디스크의 디스크 recovery_wim 의 파일 `deploy.cmd <sys_disk> <recovery_wim>` 이름입니다.   앞에서 복사한 WIM 파일입니다.
8. USB 드라이브를 제거한 다음 장치를 다시 시작합니다.

### <a name="microsoft"></a>Microsoft 

Microsoft Surface 디바이스에는 각 모델에 특정한 "베어 메탈 [복구"](https://support.microsoft.com/en-us/surfacerecoveryimage) 이미지가 포함되어 있습니다. 이러한 이미지를 사용하여 디바이스의 이미지를 다시 그 수 있습니다.

이러한 이미지는 WinRE(Windows Recovery Environment)를 사용하며 이 프로세스는 수동 프로세스(자동화되지 않습니다.)입니다. Surface용 USB 복구 드라이브 [만들기 및 사용의 단계를 따릅니다.](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)


### <a name="universal-image"></a>유니버설 이미지
Microsoft Managed Desktop 사용할 수 있는 Windows 10 Pro 및 Microsoft 365 앱 Enterprise 이미지가 Microsoft Managed Desktop. 그러나 가능하면 제조업체에서 제공하는 Microsoft Managed Desktop 적합한 이미지를 사용하는 것이 가장 좋습니다. 이는 이전 Windows 버전이면 사용자가 로그인한 후 업데이트해야 하는 경우에도 해당됩니다. 유니버설 Microsoft Managed Desktop 사용하는 것이 최종 옵션입니다.

- 30-60일마다 최신 Windows 품질 업데이트로 이미지를 업데이트하고 1년에 Microsoft 365 앱 Enterprise 업데이트에 대해 업데이트합니다.
- 이 이미지에는 복구 시나리오에 따라 복구 Microsoft 365 앱 Enterprise 복구 Windows 패키지가 포함되어 있습니다.
- USB 드라이브를 사용하여 이미지를 배포할 수 있습니다. 이미지에 포함된 설명서에 설명된 드라이버를 삽입하는 스크립트 가능한 프로세스가 포함되어 있습니다.
- 포함된 스크립트 및 폴더를 수정하여 특정 누적 업데이트 추가, 파일 복사 코드 추가, 기타 검사 수행 등 다른 사용자 지정에 사용할 수 있습니다.
- USB 드라이브에서 배포하는 Windows 드라이버 및 품질 업데이트가 추가됩니다.

> [!NOTE]
> 필요한 드라이버를 모두 추가하고, 모든 테스트를 수행하고, 최종 배포된 이미지에 문제가 없는지 보장하는 것은 귀하의 책임입니다. "있는 경우" 유니버설 이미지를 제공하지만 기술 지침과 질문에 대한 답변을 제공합니다. 연락처 MMDImage@microsoft.com.

관리 포털에서 변경 요청을 만들어 유니버설 이미지 콘텐츠 및 설명서에 대한 요청을 [제출합니다.](../get-started/access-admin-portal.md)


