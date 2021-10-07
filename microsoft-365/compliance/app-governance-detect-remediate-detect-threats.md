---
title: 앱 위협 교정
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: 앱 위협을 교정합니다.
ms.openlocfilehash: 05106b9aaf790f92e8b69bfe14b393c45c934862
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193366"
---
# <a name="remediate-app-threats"></a>앱 위협 교정

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Microsoft 365 준수 센터의 Microsoft 앱 거버넌스 섹션에 있는 **경고** 페이지를 통해 Microsoft 365 테넌트에 대한 앱 위협을 교정합니다.

![Microsoft 365 준수 센터의 앱 거버넌스 경고 요약 페이지.](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

기본적으로 **경고** 페이지에는 앱 거버넌스에서 생성한 새 위협 경고와 활성 앱 정책에서 생성한 정책 기반 경고가 나열됩니다. 특정 경고를 선택하면 추가 경고 정보와 경고 상태 변경 기능이 있는 경고 창이 열립니다. 여기서 세부 정보를 볼 수 있습니다.

![Microsoft 365 준수 센터의 앱 거버넌스 경고 세부 정보 페이지.](..\media\manage-app-protection-governance\mapg-cc-alerts-alert.png)

이 창에서 다음 추가 정보를 확인할 수 있습니다.

- **설명** 필드의 경고에 관한 추가 세부 정보.
- **정책 이름** 필드의 경고를 생성한 앱 정책의 이름. **정책 보기** 를 선택하여 경고를 생성한 앱 정책으로 이동할 수도 있습니다.

**작업** 에서 자동 수정을 구성한 앱 정책의 상태는 **해결됨** 으로 표시됩니다.

다음 단계를 사용하여 앱 경고를 교정할 수 있습니다.

1. 조사: 경고의 정보를 살펴보고 상태를 **진행 중으로 표시** 로 변경합니다.
2. 해결 방법: 조사 후 테넌트의 앱 정책 변경 결정 또는 계속되는 앱 지원 필요에 따라 상태를 **해결됨** 으로 변경합니다.

앱 경고 패턴에 따라 적절한 앱 정책을 업데이트하고 **작업** 설정을 변경하여 자동 수정을 수행할 수 있습니다. 이렇게 하면 앱 정책에 의해 생성되는 향후 경고를 조사하고 수동으로 해결할 필요가 없습니다. 자세한 내용은 [앱 정책 관리](app-governance-app-policies-manage.md)를 참조하세요.
