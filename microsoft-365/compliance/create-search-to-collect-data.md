---
title: 검색 만들기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 47d30cb2da91eff1260ffcf07838bd066917b4a1
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610645"
---
# <a name="create-a-search"></a>검색 만들기

사례에 있는 **검색** 탭에서 **새 검색** 을 클릭 하 고 마법사를 수행 하 여 새 검색을 만들 수 있습니다.

![고급 eDiscovery 사례의 검색 마법사](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>검색의 이름을 지정 하 고 설명을 입력 합니다.

케이스가 포함 된 각 검색의 이름은 고유 해야 합니다. 선택적으로 검색에 대 한 설명을 제공할 수 있습니다. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>검색할 custodians 및 custodial 위치 선택

사례에 추가한 custodians를 지정 하 여 custodian 콘텐츠 위치를 검색 하도록 선택 합니다. Custodian를 선택 하 여 custodian에 매핑된 모든 데이터 원본에 대해 검색을 실행 합니다. 또한 각 custodian에 대해 선택한 데이터 원본으로 검색 범위를 좁히는 옵션을 사용할 수 있습니다. Custodians을 추가 하 고 데이터 원본을 관리 하는 방법에 대 한 자세한 내용은 [Work with custodians](managing-custodians.md)을 참조 하십시오.

## <a name="choose-non-custodial-locations"></a>비 custodial 위치 선택

Custodian와 연결 되지 않은 데이터 원본을 검색 해야 하는 경우도 있습니다. 이 경우 검색할 위치를 지정 하거나, 모든 Exchange 사서함 또는 모든 SharePoint 사이트 및 OneDrive 계정을 검색 하는 등 특정 Office 365 서비스의 모든 콘텐츠 위치를 검색 하도록 선택할 수 있습니다.

## <a name="define-the-search-query-and-conditions"></a>검색 쿼리 및 조건 정의

미리 작성 된 조건 카드를 사용 하거나 KQL (키워드 쿼리 언어)를 사용 하 여 검색에 대 한 키워드 쿼리 및 조건을 정의할 수 있습니다. 자세한 내용은 [빌드 검색 쿼리](building-search-queries.md)를 참조 하십시오.
