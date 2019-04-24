---
title: Contoso Corporation의 고도로 기밀 디지털 자산을 위한 SharePoint Online 사이트
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '요약: Contoso가 높은 규제 대상 데이터에 대 한 SharePoint Online 사이트를 구현 하 여 조사 팀 간의 공동 작업을 보다 쉽게 수행할 수 있도록 합니다.'
ms.openlocfilehash: c20e3a1c4ad0b862e81b897acc1462e3a1d1f776
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289230"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Contoso Corporation의 고도로 기밀 디지털 자산을 위한 SharePoint Online 사이트

 **요약:** Contoso에서 높은 규제 대상 데이터에 대 한 SharePoint Online 사이트를 구현 하 여 조사 팀 간의 공동 작업을 보다 쉽게 수행할 수 있도록 합니다.
  
Contoso의 가장 귀중 한 자산은 특허 제조 기술 및 개발 중인 제품에 대 한 디자인 사양과 같은 영업 비밀의 형태로 지적 재산입니다. 이러한 자산은 디지털 형식으로, 원래는 SharePoint Server 2016 사이트에 파일로 저장 됩니다. Contoso는 Microsoft 365 Enterprise를 배포한 경우 파리, 모스크바, 뉴욕, 베이징 및 Bangalore의 조사 팀에서 보다 쉽게 액세스 하 고 공동 작업을 수행할 수 있도록 온-프레미스 디지털 자산을 클라우드로 전환 하려고 했습니다. 
  
그러나 중요 한 특성으로 인해 이러한 파일에 대 한 액세스는 다음과 같아야 합니다.

- SharePoint 관리자만 관리 하는 사이트에 대 한 지속적인 사용 권한을 사용 하 여 보거나 변경할 수 있는 사용자 집합으로 제한 됩니다. 
- 사용자가 사이트 외부로 배포 하지 못하도록 DLP (데이터 손실 방지)로 보호 됩니다.
- 암호화 및 보호 된 액세스 제어 목록을 사용 하 여 권한 없는 사용자가 사이트 외부에서 배포 된 경우에도 콘텐츠에 액세스할 수 없도록 합니다.

Contoso의 IT 부서에서 보안 및 sharepoint 관리자는 [높은 규제 대상 데이터에 대 한 sharepoint Online 사이트](teams-sharepoint-online-sites-highly-regulated-data.md)를 사용 하기로 결정 했습니다.
  
Contoso는 이러한 단계를 사용 하 여 연구 팀을 위한 SharePoint Online 팀 사이트를 만들고 보호 합니다.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>1 단계: 연구 팀 그룹의 구성원을 검토 하 고 확인 함

Contoso IT 관리자는 리서치 팀에 대 한 보안 그룹 집합을 검토 했습니다. 사용자가 연구원을 선택 하지 않았거나 자산을 조사 하기 위해 액세스 하지 않아도 되는 사람은 제거 되었습니다. 

또한 다음과 같은 새 보안 그룹을 만듭니다.

- **관리자**  사용 권한 수정 기능을 포함 하 여 사이트에 대 한 모든 권한을 가지는 SharePoint 관리자 집합입니다.
- **리서치-구성원**  전 세계의 연구 팀에 대 한 보안 그룹 집합입니다.
- **리서치-뷰어**  리서치 조직의 임원 같은 사이트의 자산을 볼 수만 있는 관리 사용자 집합입니다.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>2 단계: 격리 된 SharePoint Online 팀 사이트 만들기 

Contoso SharePoint 관리자가 먼저 **Research**라는 새 팀 사이트를 만들었습니다. 그런 다음 다음을 구성 합니다.

- **관리자 수준의** 보안 그룹을 구성원으로 갖는 리서치 소유자 SharePoint 그룹을 사용 하기 위한 모든 권한 수준입니다.
- **리서치** 구성원 보안 그룹을 구성원으로 가진 리서치 구성원 SharePoint 그룹을 사용 하기 위한 편집 권한 수준입니다.
- **리서치** 방문자 보안 그룹을 구성원으로 포함 하는 리서치 방문객 SharePoint 그룹을 사용할 수 있는 읽기 권한 수준입니다.

다음은 sharepoint 사용 권한 수준, sharepoint 그룹 및 해당 구성원에 대 한 결과입니다.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

다음으로, 사이트에 대 한 추가 제한을 구성 합니다.

구성에 대 한 자세한 내용은 [격리 된 SharePoint Online 팀 사이트 배포](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)를 참조 하세요.

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a>3 단계: 제한적인 DLP 정책에 맞게 사이트 구성

첫째로, Contoso 관리자는 **리서치** 사이트에 **고도로 기밀** Office 365 보존 레이블을 적용 했습니다.

다음으로, 다음은 **Research** 라는 새 Office 365 DLP 정책을 만들었습니다.

- **높은 수준의 기밀** Office 365 보존 레이블을 사용 합니다. 
- **리서치** 사이트에 적용 됩니다.
- 사용자가 문서를 공유할 수 없습니다.

구성에 대 한 자세한 내용은 [Office 365 레이블 및 DLP를 사용 하 여 SharePoint Online 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)를 참조 하세요.

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>4 단계: 사이트에 대 한 Azure Information Protection 하위 레이블 만들기

Contoso 관리자는 다음과 같은 범위가 지정 된 정책에서 기본 **고도로 기밀** 레이블 **Research** 라는 새로운 Azure Information Protection 하위 레이블을 만들었습니다.

- 암호화 필요
- **연구-구성원** 보안 그룹 구성원의 모든 권한을 허용 합니다.
- **리서치-뷰어** 보안 그룹의 구성원에 게 읽기 액세스를 허용 합니다.

다음으로, Azure Information Protection 클라이언트를 연구 팀 구성원의 장치에 배포 했습니다.

구성에 대 한 자세한 내용은 [Azure Information Protection을 사용 하 여 SharePoint Online 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)를 참조 하세요. 

높은 기밀 자산에 대 한 **리서치** 사이트의 결과 구성은 다음과 같습니다.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

**리서치** 사이트의 폴더에 있는 파일은 다음과 같은 방법으로 보호 됩니다.

- 리서치 **** Azure Information Protection sublabel- **리서치** 사이트에서 이동 하거나 복사할 때 파일과 함께 이동 하는 각 파일에 암호화 및 permssions를 적용 합니다.
- **중요 한** 보존 레이블과 파일을 사이트에 남기지 않도록 하는 설정을 사용 하는 **연구** DLP 정책입니다.
- 리서치- **구성원** 및 연구 보안 그룹의 구성원에 대 한 액세스를 허용 하는 사이트 **** 권한 집합을 사용 하 고,이를 관리 하 **** 는 데 사용할 수 있습니다.

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>5 단계: 온-프레미스 SharePoint 조사 데이터 마이그레이션

Contoso 관리자가 온-프레미스 sharepoint Server 2016 사이트의 모든 온-프레미스 조사 파일을 새 **리서치** SharePoint Online 사이트의 폴더로 이동 했습니다.

## <a name="step-6-trained-their-users"></a>6 단계: 사용자 교육 

Contoso 보안 직원은 조사 팀을 단계별로 진행 하는 필수 과정을 담당 합니다.

- 새 **리서치** SharePoint Online 사이트 및 기존 파일에 액세스 하는 방법
- 사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법
- DLP 정책이 외부에서 파일을 공유 하지 못하도록 차단 하는 방법에 대 한 데모입니다.
- Azure Information Protection 클라이언트를 사용 하 여 리서치 하위 레이블로 조사 파일에 **** 레이블을 지정 하는 방법
- **리서치** 하위 레이블이 사이트에서 누설 된 경우에도 파일을 보호 하는 방법을 보여 주는 예제입니다.

최종 결과는 보안 환경에서 조직 전체에서 공동 작업을 수행할 수 있는 안전한 환경입니다. 

리서치 하위 레이블이 포함 된 조사 **** 문서가 **리서치** 사이트에서 누설 되는 경우에는 암호화 되 고 유효한 자격 증명을 가진 리서치- **검토자** 보안 그룹의 구성원 에게만 액세스 가능 합니다. ****

## <a name="next-step"></a>다음 단계

[배포](deploy-microsoft-365-enterprise.md) 조직의 Microsoft 365 Enterprise

