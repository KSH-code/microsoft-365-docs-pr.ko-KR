---
title: 자동화 파일 업로드 관리
description: 콘텐츠 분석을 사용하도록 설정하고 분석을 위해 제출할 파일 확장명 및 전자 메일 첨부 파일 확장명 구성
keywords: 자동화, 파일, 업로드, 콘텐츠, 분석, 파일, 확장명, 전자 메일, 첨부 파일
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c89b5b676e25b23e0e5fdfb925f6894647cb41e5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220444"
---
# <a name="manage-automation-file-uploads"></a>자동화 파일 업로드 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

자동화된 조사에서 추가 검사를 위해 특정 파일 및 전자 메일 첨부 파일을 클라우드에 자동으로 업로드할 수 있도록 콘텐츠 분석 기능을 사용하도록 설정하세요.

파일 확장명 이름과 전자 메일 첨부 파일 확장명을 지정하여 파일 및 전자 메일 첨부 파일을 식별합니다.

예를 들어 *exe* 및 *bat을* 파일 또는 첨부 파일 확장명 이름으로 추가하는 경우 자동화된 조사 중에 추가 검사를 위해 해당 확장명을 가지는 모든 파일 또는 첨부 파일이 자동으로 클라우드로 전송됩니다.

## <a name="add-file-extension-names-and-attachment-extension-names"></a>파일 확장명 이름과 첨부 파일 확장명을 추가합니다.

1. 탐색 창에서 **끝점 규칙 설정** \>  \>  \> **업로드를 선택합니다.**

2. 설정 및 해제 간에 콘텐츠 분석 **설정을** **전환합니다.**

3. 다음 내선 이름과 별도의 내선 이름을 각자 콤보로 구성합니다.
   - **파일 확장명** - 추가 검사를 위해 전자 메일 첨부 파일이 제출되는 것을 제외한 의심스러운 파일

## <a name="related-topics"></a>관련 항목

- [자동화 폴더 제외 관리](manage-automation-folder-exclusions.md)
