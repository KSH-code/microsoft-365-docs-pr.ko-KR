---
title: SKOS 기반 형식을 사용하여 용어 집합 가져오기
description: SKOS 기반 형식을 사용하여 용어 집합 가져오는 방법 알아보기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210842"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>SKOS 기반 형식을 사용하여 용어 집합 가져오기

SKOS 기반 형식을 사용하여 용어 집합을 가져올 수 있습니다. 형식에 대한 자세한 내용은 [SharePoint 분류로 된 SKOS 형식 참조](skos-format-reference.md) 보기 이 기능을 사용하려면 [SharePoint Syntex](index.md) 라이선스가 필요합니다.

가져오는 파일의 용어가 20,000개 이하인 것이 좋습니다. 파일이 커지면 유효성 검사와 가져오기에 걸리는 시간이 늘어날 수 있습니다.

1. SharePoint 관리 센터에서 **콘텐츠 서비스** 를 확장하고 **용어 저장소** 를 클릭합니다.

2. 용어 집합을 가져올 용어 그룹을 선택합니다.

3. 명령 모음에서 **용어 집합 가져오기** 를 클릭합니다.

4. 서식 파일로 사용 할 샘플 파일을 다운로드 하려는 경우 **sample-metadata.ttl** 을 클릭하여 SKOS 기반 형식을 사용하는 샘플 파일을 가져옵니다.

5. 가져올 용어 및 용어 집합이 포함 된 가져오기 파일을 만듭니다.

6. **파일 형식** 에서 **SKOS(*.ttl)** 을 선택합니다.

7. **찾아보기** 를 클릭하여 가져오기 파일을 탐색하고 추가합니다.

8. **가져오기** 를 클릭합니다. 가져오기가 완료 될 때까지 패널을 닫지 마세요.

파일 가져오기가 완료되면 성공 메시지가 표시되고, 용어 저장소가 새로고침 되면 새로 만들어진 용어 집합으로 이동할 수 있습니다.

## <a name="see-also"></a>참고 항목

[관리되는 메타데이터 소개](/sharepoint/managed-metadata)

[문서 이해 개요](document-understanding-overview.md)

[용어 집합 가져오기(사이트 수준)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
