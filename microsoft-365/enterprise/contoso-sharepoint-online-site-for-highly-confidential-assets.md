---
title: Contoso Corporation의 기밀 사항이 디지털 자산에 대 한 SharePoint Online 사이트
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: '요약: Contoso에 대 한 SharePoint Online 사이트를 매우 구현 하는 방법의 연구 (영문) 간의 보다 쉽게 공동 작업에 대 한 규제 데이터 팀 합니다.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870310"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Contoso Corporation의 기밀 사항이 디지털 자산에 대 한 SharePoint Online 사이트

 **요약:** Contoso의 연구 팀 간에 쉽게 공동 작업에 대 한 매우 규제 데이터에 대 한 SharePoint Online 사이트 구현 하는 방법입니다.
  
Contoso의 가장 중요 한 자산 영업 비밀 독점 제조 기술 등의 형태로 지적 재산 되며 개발에 있는 제품에 대 한 사양을 디자인 합니다. 이러한 자산이 디지털 폼을 원래 SharePoint Server 2016 사이트에 파일로 저장 합니다. Contoso Microsoft 365 엔터프라이즈를 배포 하는 경우에 쉽게 액세스 하 고 더 개방 공동 작업에 대 한 클라우드로의 온-프레미스 디지털 자산 파리, 모스크바, 뉴욕, 베이징, 및 Bangalore 연구팀 간에 전환 하려면 이와 더불어 합니다. 
  
그러나가 중요 한 특성으로 인해 이러한 파일에 대 한 액세스 이어야 합니다.

- 보거나, SharePoint 관리자에 의해만 관리 사이트에 대 한 지속적인 사용 권한으로 변경할 수 있는 사용자의 집합으로 제한 합니다. 
- 와 방지 DLP (데이터 손실) 사용자가 사이트 외부이 배포 하지 못하도록 보호를 받습니다.
- 암호화 된 및와 제한 된 액세스 제어 사이트 외부 배포 되는 경우에 권한이 없는 사용자가 해당 내용을 액세스 하지 못하도록 방지 하기 위해 목록입니다.

Contoso의 보안 및 SharePoint 관리자의 IT 부서 하기로 결정 [에 대 한 SharePoint Online 사이트의 데이터를 매우 규제 된](teams-sharepoint-online-sites-highly-regulated-data.md)을 사용 합니다.
  
Contoso를 만들고 해당 연구 (영문) 팀에 대 한 SharePoint Online 팀 사이트를 보호 하려면 다음이 단계를 사용 합니다.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>1 단계: 검토 하 고 연구 팀 그룹의 구성원 확인

Contoso IT 관리자의 경우 해당 연구 (영문) 팀에 대 한 보안 그룹 집합의 검토를 수행합니다. 즉를 연구원 없거나 연구 (영문) 자산에 대 한 액세스를 필요 하지 않은 사용자가 모두 제거 합니다. 

이러한도 이러한 새 보안 그룹을 작성 하 고 있습니다.

- **Admins 연구 (영문)**  사용 권한을 수정 하는 기능을 포함 하 여 사이트에 대 한 모든 권한을 포함 된 SharePoint admins 그룹의 집합입니다.
- **리서치 구성원**  전세계 연구팀에 대 한 보안 그룹의 집합입니다.
- **리서치 뷰어**  사이트에서 자산을 볼 수 있는 연구 (영문) 조직에서 중역 같은 관리 사용자의 집합입니다.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>2 단계: 격리 된 SharePoint Online 팀 사이트를 만든 

새 팀 사이트를 처음 만든 Contoso SharePoint admins 라는 **연구 (영문)**. 서비스 응용 프로그램이 다음 구성 합니다.

- **리서치 Admins** 보안 그룹 구성원으로 있는 리서치 Owners SharePoint 그룹을 사용 하 여 모든 권한 사용 권한 수준
- **리서치 구성원** 보안 그룹 구성원으로 있는 리서치 Members SharePoint 그룹을 사용 하 여 편집 사용 권한 수준
- **리서치 뷰어** 보안 그룹 구성원으로 있는 리서치 방문자 SharePoint 그룹을 사용 하 여 읽기 권한 수준

다음은 결과 SharePoint 사용 권한 수준, SharePoint 그룹 및 해당 멤버입니다.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

다음으로, 서비스 응용 프로그램이 사이트에 대 한 추가 제한을 구성 합니다.

구성 세부 정보에 대 한 [SharePoint Online 팀 사이트를 격리 된 배포](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)를 참조 합니다.

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a>3 단계: 제한적인 Office 365 레이블 DLP 정책에 대 한 사이트 구성

첫째, Contoso admins **기밀 사항이** Office 365 레이블 **연구 (영문)** 사이트에 적용 된 합니다.

새로 만든 다음으로, Office 365 DLP 정책 이라는 **연구 (영문)는** :

- **기밀 사항이** Office 365 레이블을 사용합니다. 
- **연구 (영문)** 사이트에 적용 됩니다.
- 사용자를가 문서를 공유할 수 없습니다.

구성 세부 정보에 대 한 [Office 365 레이블 및 DLP 사용 하 여 SharePoint Online 보호 파일](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)을 참조 합니다.

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>4 단계: 사이트에 대 한는 Azure 정보 보호 하위 레이블 생성

Azure 정보 보호 하위 레이블을 새로 만든 Contoso admins 라는 하는 범위가 지정 된 정책에서 기본 **기밀 사항이** 레이블의 **연구 (영문)** :

- 암호화가 필요합니다.
- **리서치 구성원** 보안 그룹의 구성원으로 전체 액세스할 수 있습니다.
- **리서치 뷰어** 보안 그룹의 구성원으로 대 한 읽기 액세스를 허용합니다.

다음으로, Azure 정보 보호 클라이언트 연구 팀 구성원의 장치에 배포 합니다.

구성 세부 정보 [Azure 정보 보호와 SharePoint Online 보호 파일](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)을 참조 하십시오. 

기밀 자산에 대 한 **연구 (영문)** 사이트의 결과 구성은 다음과 같습니다.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>5 단계: 온-프레미스 SharePoint 연구 (영문) 데이터 마이그레이션

Contoso admins 새로운 **연구** SharePoint Online 사이트의 폴더를 온-프레미스 SharePoint Server 2016 사이트에서 파일을 연구 온-프레미스의 모든 이동 합니다.

## <a name="step-6-trained-their-users"></a>6 단계: 사용자에 게 교육 

Contoso 보안 직원이 사용 하 여 게시할 때는 단계별로 하는 필수 과정에서 연구팀 교육:

- 새 **연구** SharePoint Online 사이트와 기존 파일에 액세스 하는 방법입니다.
- 사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법
- DLP 정책에서 외부에서 공유 되지 않도록 파일을 차단 하는 방법의 데모입니다.
- 레이블을 지정 **하는 리서치** 하위 레이블이 있는 연구 (영문) 파일을 Azure 정보 보호 클라이언트를 사용 하는 방법입니다.
- 사이트에서가 유출 된 경우에 **연구 (영문)** 하위 레이블 파일을 보호 하는 방법의 데모입니다.

최종 결과 안전한 환경은 연구원 안전한 환경에서 조직 전체에서 공동 작업할 수 있습니다. 

**연구 (영문)** 하위 레이블이 있는 연구 (영문) 문서 **연구 (영문)** 사이트에서 유출 되, 암호화 하 고 유효한 자격 증명을 사용 **하는 리서치 구성원** 및 **연구 뷰어** 보안 그룹의 구성원에만 액세스할 수는 있습니다.

## <a name="next-step"></a>다음 단계

조직에 Microsoft 365 Enterprise를 [배포](deploy-microsoft-365-enterprise.md)합니다.

