---
title: SharePoint Online 최신 사이트 페이지에서 이미지 최적화
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: SharePoint Online에 포함된 도구를 사용하여 온라인 최신 사이트 페이지의 이미지를 최적화하는 SharePoint 방법을 학습합니다.
ms.openlocfilehash: 85280dfc903c56c89308c50fa94979fd98b2003c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168509"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a>SharePoint Online 최신 사이트 페이지에서 이미지 최적화

이 문서는 SharePoint Online 최신 사이트 페이지에서 이미지를 최적화하는 방법의 이해를 돕습니다.

클래식 게시 사이트에서 이미지 최적화에 대한 자세한 내용은 [SharePoint Online용 이미지 최적화](image-optimization-for-sharepoint-online.md)를 참조하세요.

>[!NOTE]
>SharePoint Online 최신 포털의 성능에 대한 자세한 내용은 [최신 SharePoint 환경의 성능](/sharepoint/modern-experience-performance)을 참조하세요.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a>SharePoint용 페이지 진단 도구를 사용한 이미지 최적화 분석

SharePoint용 페이지 진단 도구는 새 Microsoft Edge에 대한 브라우저 확장입니다. (SharePoint Online 최신 포털 및 클래식 게시 사이트 페이지를 분석하는 https://www.microsoft.com/edge) 및 Chrome 브라우저) 이 도구는 정의된 성능 기준의 집합 대비 페이지 수행 방식을 보여주는 분석된 각 페이지에 대한 보고서를 제공합니다. Sharepoint용 페이지 진단 도구에 대해 배우고 설치하려면[Sharepoint Online에 페이지 진단 도구 사용](page-diagnostics-for-spo.md)을 참조하세요.

>[!NOTE]
>페이지 진단 도구는 SharePoint Online에서만 사용할 수 있으며 SharePoint 시스템 페이지에서는 사용할 수 없습니다.

SharePoint용 페이지 진단 도구를 사용하여 SharePoint 최신 사이트를 분석할 때 _진단 테스트_ 창에서 대용량 이미지에 대한 정보를 확인할 수 있습니다.

가능한 결과는 다음과 같습니다.

- **주의 필요** (빨간색): 페이지에 크기가 300KB 이상인 이미지가 **하나 이상** 포함되어 있음
- **조치 필요하지 않음** (녹색): 페이지에 크기가 300KB 이상인 이미지가 포함되어 있지 않음

**대용량 이미지 검색** 결과가 **주의 필요** 구역에 나타나면 결과를 클릭하여 추가 세부 정보를 볼 수 있습니다.

![페이지 진단 도구 결과입니다.](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a>대용량 이미지 문제 수정

페이지에 크기가 300KB 이상인 이미지를 포함하는 경우 **대용량 이미지 검색 결과** 를 선택하여 대용량 이미지를 확인합니다. 최신 SharePoint Online 페이지에서 이미지 변환은 브라우저 창의 크기와 클라이언트 모니터의 해상도에 따라 자동으로 제공되고 크기가 조정됩니다. SharePoint Online에 업로드하기 전에 웹 사용을 위해서는 항상 이미지를 최적화해야 합니다. 대용량 이미지의 크기와 해상도가 자동으로 줄어들며 예기치 않은 렌더링 특성이 생길 수 있습니다.

성능 문제 개선을 위해 페이지를 수정하기 전에 분석 결과에 페이지 로드 시간을 기록해 둡니다. 수정 후에 다시 도구를 실행하여 새 결과가 기준선 표준에 포함되는지 확인하고 새 페이지 로드 시간을 확인하여 개선이 되었는지 확인합니다.

![페이지 로드 시간 결과입니다.](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>페이지 로드 시간은 네트워크 부하, 하루 중 시간 및 기타 일시적인 조건과 같은 다양한 요인에 따라 다를 수 있습니다. 결과의 평균을 내는데 도움이 되도록 수정을 하기 전과 후에 페이지 로드 시간을 몇 번 정도 테스트해야 합니다.

## <a name="related-topics"></a>관련 항목

[SharePoint Online 성능 조정](tune-sharepoint-online-performance.md)

[Office 365 성능 조정](tune-microsoft-365-performance.md)

[최신 SharePoint 환경의 성능](/sharepoint/modern-experience-performance)

[콘텐츠 배달 네트워크](content-delivery-networks.md)

[sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기](use-microsoft-365-cdn-with-spo.md)