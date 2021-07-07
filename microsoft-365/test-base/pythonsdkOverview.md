---
title: Python용 테스트 기본 SDK
description: Python용 테스트 베이스의 SDK 이해에 대한 세부 정보
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323125"
---
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="39b29-103">Python용 테스트 기본 SDK</span><span class="sxs-lookup"><span data-stu-id="39b29-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="39b29-104">개요</span><span class="sxs-lookup"><span data-stu-id="39b29-104">Overview</span></span>
<span data-ttu-id="39b29-105">테스트 기본 SDK를 사용하여 Azure 테스트 기본 리소스와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b29-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="39b29-106">(예: 응용 프로그램 패키지 관리, 패키지 만들기, 패키지 편집 및 패키지 삭제 포함)</span><span class="sxs-lookup"><span data-stu-id="39b29-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="39b29-107">SDK를 사용하여 스크립트Execution, 안정성, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression 등 테스트 요약 및 분석 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b29-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="39b29-108">테스트 기준 SDK를 사용하여 CI/CD 파이프라인에 테스트 기준을 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b29-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="39b29-109">클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="39b29-109">Client Library</span></span>

<span data-ttu-id="39b29-110">pip와 함께 테스트 기본 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="39b29-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="39b29-111">예제</span><span class="sxs-lookup"><span data-stu-id="39b29-111">Example</span></span>
