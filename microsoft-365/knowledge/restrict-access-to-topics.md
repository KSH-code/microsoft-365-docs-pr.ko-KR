---
title: 특정 항목의 항목에 Microsoft Viva 제한
description: 항목을 검색하지 못하게 제외하는 방법
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187756"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>특정 항목의 항목에 Microsoft Viva 제한

이 Microsoft Viva 조직의 이해 관계자는 특정 항목을 검색하여 라이선스가 부여된 사용자에게 노출되지 않는지 확인하려는 경우도 있습니다. 예를 들어 아직 정보를 노출하지 않을 프로젝트에서 작업할 수 있습니다. 사이트에 Office 365, 파일 및 기타 리소스에 대한 사용 권한을 설정하면 항목 환경 사용자가 항목에서 중요한 정보를 볼 수 없는 반면, 특정 항목을 검색하지 못하도록 하는 추가 보호책이 있습니다.

지식 관리자는 항목을 검색하지 못하게 하는 설정을 제어하는 반면, 지식 관리자 및 기타 관련자는 공동 작업할 수 있도록 작업 수행 방법을 알아야 합니다.

> [!Important] 
> 이 문서에서는 항목을 AI를 통해 식별되거나 사용자 환경에서 추가 보안 보호책으로 볼 수 있는 방법을 설명합니다. Viva 항목에서는 사용자가 모든 권한을 통해 액세스할 수 없는 항목의 항목을 볼 Office 365 중요합니다. 사용자가 항목을 볼 수 있는 경우에도 해당 파일, 사이트 및 페이지에 보기 권한이 Office 365 페이지가 표시되지 않습니다. 중요한 파일에 대한 사용 권한이 올바르게 설정되어 있는지 확인하려면 기본 보안 보호 조치가 필요합니다.

## <a name="prevent-topics-from-being-identified"></a>항목을 식별하지 못하게 방지

지식 관리자는 초기 인덱싱에서 해당 항목을 찾지 못하도록 하여 특정 항목에 대한 액세스를 제한할 수 있습니다. 이 작업을 수행하기 위한 두 가지 방법은 다음의 Viva 항목 관리 설정에서 Microsoft 365 관리 센터.
 
- [항목 SharePoint](./topic-experiences-discovery.md#select-sharepoint-topic-sources)제외할 사이트 선택 : 이 설정을 사용하여 특정 SharePoint 사이트가 항목에 대해 크롤링되지 않도록 할 수 있습니다.
- [이름으로 항목 제외:](./topic-experiences-discovery.md#exclude-topics-by-name)관리자는 이 설정을 사용하여 특정 항목을 이름으로 검색하지 못하도록 할 수 있습니다. Viva 항목 관리 설정에서 관리자는 CSV 파일에서 제외할 항목 목록을 업로드할 수 있습니다. 항목 이름과 정확히 일치하거나 부분적으로 일치하는 항목을 제외할 수 있습니다.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>특정 사용자가 항목을 볼 수 없습니다.

지식 관리자는 조직에서 항목을 볼 수 있는 [사용자도 선택할 수 있습니다.](./topic-experiences-knowledge-rules.md) 이 설정을 사용하면 모든 항목을 볼 수 있는 라이선스가 있는 사용자를 선택할 수 있습니다. 예를 들어 파일럿 환경에서는 소수의 사용자만 항목을 볼 수 있도록 허용할 수 있습니다.

## <a name="remove-topics-from-being-viewed"></a>항목을 보지 못하게 제거

지식 관리자는 사용자가 [](./manage-topics.md) 더 이상 볼 수 없는 항목을 제거할 수 있습니다. 항목 **관리 페이지의** 항목 센터에서 기술 관리자는 특정 항목을 거부하여 항목을 볼 수 없습니다. 추천 상태나 확인된 상태와 관계없이 항목을 제거할 수 있습니다.

제거된 항목은 나중에 필요한 경우 다시 볼 수 있는 항목으로 추가할 수 있습니다. 


## <a name="see-also"></a>참고 항목



