---
title: 장치 태그 만들기 및 관리
description: 장치 태그를 사용하여 디바이스를 그룹화하여 컨텍스트를 캡처하고 인시던트의 일부로 동적 목록 만들기를 사용하도록 설정
keywords: 태그, 장치 태그, 장치 그룹, 그룹, 수정, 수준, 규칙, aad 그룹, 역할, 할당, 순위
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 38b5d3f2ddcab56fc712c771019982d05a18e20e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199756"
---
# <a name="create-and-manage-device-tags"></a>장치 태그 만들기 및 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

디바이스에 태그를 추가하여 논리적 그룹 소속을 만듭니다. 디바이스 태그는 네트워크의 적절한 매핑을 지원하므로 다양한 태그를 연결하여 컨텍스트를 캡처하고 인시던트 일부로 동적 목록 만들기를 사용하도록 설정할 수 있습니다. 태그는 장치 목록 보기에서  필터로 사용할 수도, 디바이스를 그룹화할 수도 있습니다. 장치 그룹화에 대한 자세한 내용은 장치 그룹 만들기 [및 관리를 참조하세요.](machine-groups.md)

다음과 같은 방법으로 디바이스에 태그를 추가할 수 있습니다.

- 포털 사용
- 레지스트리 키 값 설정

> [!NOTE]
> 디바이스에 태그를 추가하는 시간과 장치 목록 및 디바이스 페이지의 가용성 사이에 몇 가지 대기 시간이 있을 수 있습니다.

API를 사용하여 디바이스 태그를 추가하려면 [디바이스 태그 API 추가 또는 제거](add-or-remove-machine-tags.md)를 참조하세요.

## <a name="add-and-manage-device-tags-using-the-portal"></a>포털을 사용하여 디바이스 태그 추가 및 관리

1. 태그를 관리할 디바이스를 선택합니다. 다음 보기 중 하나에서 디바이스를 선택하거나 검색할 수 있습니다.

   - **보안 작업 대시보드** - 활성 경고가 있는 상위 디바이스 섹션에서 장치 이름을 선택합니다.
   - **경고 큐** - 경고 큐에서 디바이스 아이콘 옆에 있는 디바이스 이름을 선택하세요.
   - **디바이스 목록** - 디바이스 목록에서 디바이스 이름을 선택하세요.
   - **검색 상자** - 드롭다운 메뉴에서 디바이스를 선택하고 디바이스 이름을 입력하세요.

     파일 및 IP 보기를 통해 경고 페이지로 이동할 수도 있습니다.

2. 응답 작업 행에서 **태그 관리** 를 선택하세요.

    :::image type="content" alt-text="태그 관리 단추의 이미지입니다." source="images/manage-tags-option.png":::

3. 태그를 찾거나 만들 입력

    :::image type="content" alt-text="device1에 태그를 추가하는 이미지입니다." source="images/create-new-tag.png":::

태그는 장치 보기에 추가된 후 장치 목록 보기에도 **반영됩니다.** 그런 다음 태그 **필터를** 사용하여 관련 장치 목록을 볼 수 있습니다.

> [!NOTE]
> 괄호가 포함된 태그 이름에는 필터링이 작동하지 않을 수 있습니다.
>
> 새 태그를 만들면 기존 태그 목록이 표시됩니다. 이 목록에는 포털을 통해 만들어진 태그만 표시됩니다. 클라이언트 장치에서 만든 기존 태그는 표시되지 않습니다.

이 보기에서 태그를 삭제할 수도 있습니다.

:::image type="content" alt-text="device2에 태그를 추가하는 이미지입니다." source="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>레지스트리 키 값을 설정하여 장치 태그 추가

> [!NOTE]
> 다음 장치에서만 적용할 수 있습니다.
>
> - Windows 11
> - Windows 10 버전 1709 이상
> - Windows 서버, 버전 1803 이상
> - Windows Server 2016
> - Windows Server 2012 R2
> - Windows Server 2008 R2 SP1
> - Windows 8.1
> - Windows 7 SP1

> [!NOTE]
> 태그에서 설정할 수 있는 최대 문자 수는 200개입니다.

태그가 비슷한 디바이스는 특정 장치 목록에 상황에 맞는 작업을 적용해야 하는 경우 편리한 장치입니다.

디바이스에 태그를 추가하려면 다음 레지스트리 키 항목을 사용합니다.

- 레지스트리 키: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- 레지스트리 키 값(REG_SZ): `Group`
- 레지스트리 키 데이터: `Name of the tag you want to set`

> [!NOTE]
> 장치 태그는 하루 한 번 생성되는 장치 정보 보고서의 일부입니다. 또는 새 장치 정보 보고서를 전송하는 끝점을 다시 시작해야 할 수도 있습니다.
>
> 위의 레지스트리 키를 사용하여 추가된 태그를 제거해야 하는 경우 'Group' 키를 제거하는 대신 레지스트리 키 데이터의 내용을 지워야 합니다.
