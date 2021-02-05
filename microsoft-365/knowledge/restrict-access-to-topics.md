---
title: Microsoft Viva 항목의 항목에 대한 액세스 제한
description: 항목을 검색하지 못하게 하는 항목을 제외하는 방법
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
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 6b3d2a4b6cbfc67623cea58b73681b7af7cc4889
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107161"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Microsoft Viva 항목의 항목에 대한 액세스 제한

Microsoft Viva에서 조직의 관련자는 특정 항목을 검색하여 사용이 허가된 사용자에게 공개하지 않을 수 있습니다. 예를 들어 아직 정보를 노출하지 않을 프로젝트를 작업 중일 수 있습니다. 사이트, 파일 및 기타 리소스에 대한 Office 365 사용 권한은 Topic Experiences 사용자가 항목에서 중요한 정보를 볼 수 없는 반면 특정 항목을 검색하지 못하도록 방지하는 추가 보호책이 있습니다.

지식 관리자는 항목 검색을 방지하기 위해 지식 네트워크 설정을 제어하는 반면, 기술 관리자 및 기타 이해 관계자는 공동 작업할 수 있도록 작업 수행 방법을 알아야 합니다.

> [!Important] 
> 이 문서에서는 AI를 통해 항목을 식별하거나 사용자 환경에서 추가 보안 보호책으로 볼 수 없습니다. Viva 항목에서는 사용자가 Office 365 권한을 통해 액세스할 수 없는 항목의 항목을 볼 수 없습니다. 사용자가 항목을 볼 수 있는 경우에도 해당 파일, 사이트 및 페이지에는 볼 수 있는 Office 365 권한이 없습니다. 중요한 파일에 대한 사용 권한이 올바르게 설정되어 있는지 확인하려면 기본 보안 보호책이 되어야 합니다.

## <a name="prevent-topics-from-being-identified"></a>항목을 식별할 수 없습니다.

지식 관리자는 초기 인덱싱에서 해당 항목을 찾지 못하도록 하여 특정 항목에 대한 액세스를 제한할 수 있습니다. Microsoft 365 관리 센터의 기술 네트워크 관리 설정에서는 두 가지 방법으로 이 작업을 할 수 있습니다.
 
- [항목 검색에서](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)제외할 SharePoint 사이트를 선택합니다. 이 설정을 사용하여 특정 SharePoint 사이트가 항목에 대해 크롤링되지 않도록 할 수 있습니다.
- [이름별](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)항목 제외: 관리자는 이 설정을 사용하여 특정 항목을 이름으로 검색하지 못하도록 할 수 있습니다. 지식 네트워크 관리 설정에서 관리자는 CSV 파일에서 제외할 항목 목록을 업로드할 수 있습니다. 항목 이름과 정확히 일치하거나 부분적으로 일치하는 항목을 제외할 수 있습니다.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>특정 사용자가 항목을 볼 수 없습니다.

지식 관리자는 조직에서 항목을 볼 수 있는 [사용자도 선택할 수 있습니다.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules) 이 설정을 사용하면 모든 항목을 볼 수 있는 사용이 허가된 사용자를 선택할 수 있습니다. 예를 들어 파일럿 환경에서는 소수의 사용자만 항목을 볼 수 있도록 허용할 수 있습니다.

## <a name="remove-topics-from-being-viewed"></a>항목을 볼 수 없습니다.

지식 관리자는 사용자가 [](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) 더 이상 항목을 볼 수 있도록 항목을 제거할 수 있습니다. 항목 관리 **페이지의** 항목 관리 페이지에서 기술 관리자는 특정 항목을 거부하여 항목을 볼 수 없습니다. 추천 상태 또는 확인된 상태의 항목에 관계없이 항목을 제거할 수 있습니다.

제거된 항목은 나중에 필요한 경우 다시 볼 수 있는 항목으로 추가할 수 있습니다. 


## <a name="see-also"></a>참고 항목



  






