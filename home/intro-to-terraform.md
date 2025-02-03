# 테라폼은 무엇인가요?

테라폼은 안전하고 효율적으로 인프라를 구축 및 변경하고 버전 관리를 하는 데 사용할 수 있습니다.

하시코프 테라폼은 코드형 인프라 도구이며 클라우드와 온프레미스 리소스들을 사람이 읽을 수 있는 구성 파일로 정의합니다. 이 파일은 버전 관리, 재사용, 공유가 가능합니다. 이를 통해 여러분은 일관된 워크플로를 사용하여 생명 주기 전반에 걸쳐 인프라를 프로비저닝하고 관리할 수 있습니다. 테라폼은 저수준 구성 요소인 컴퓨팅 인스턴스, 스토리지, 네트워킹부터 고수준 구성 요소인 DNS 레코드와 Saas 기능까지 관리할 수 있습니다.

> **실습**: 시작하기 튜토리얼을 따라가면서 주요 클라우드 서비스의 인프라를 관리해 봅시다.
>
> <!-- TODO Link the document below after translating it -->
> [아마존 웹 서비스](https://developer.hashicorp.com/terraform/tutorials/aws-get-started), [애저](https://developer.hashicorp.com/terraform/tutorials/azure-get-started), [구글 클라우드 플랫폼](https://developer.hashicorp.com/terraform/tutorials/gcp-get-started), [오라클 클라우드 인프라스트럭처](https://developer.hashicorp.com/terraform/tutorials/oci-get-started), [도커](https://developer.hashicorp.com/terraform/tutorials/docker-get-started)

## 테라폼은 어떻게 동작하나요?

테라폼은 애플리케이션 프로그래밍 인터페이스(API)로 클라우드 플랫폼과 다른 서비스의 리소스를 생성하고 관리합니다. 프로바이더는 이용할 수 있는 API를 사용하여 테라폼이 거의 모든 플랫폼이나 서비스에서 작동하도록 지원합니다.

``` mermaid
graph LR
    T[테라폼] <--> TP[테라폼 프로바이더]
    TP[테라폼 프로바이더] <--> TA[대상 API]
```

> <!-- TODO Link the document below after translating it -->
하시코프와 테라폼 커뮤니티는 여러 유형의 리소스와 서비스를 관리하기 위해 이미 수천 개의 프로바이더를 만들었습니다. 공개적으로 사용할 수 있는 프로바이더는 [테라폼 레지스트리](https://registry.terraform.io/)에서 찾아볼 수 있습니다. 여기에는 아마존 웹 서비스(AWS), 애저, 구글 클라우드 플랫폼(GCP), 쿠버네티스, 헬름, 깃허브, 스플렁크, 데이터독을 비롯해 많은 것이 포함되어 있습니다.

핵심적인 테라폼 워크플로는 세 단계로 구성됩니다.

- 작성: 하나 또는 여러 클라우드 프로바이더와 서비스에 대한 리소스를 정의합니다. 예를 들어, 보안 그룹과 로드 밸런서와 함께 가상 프라이빗 클라우드(VPC) 안에 있는 가상 머신에서 애플리케이션을 배포하는 환경을 구성할 수 있습니다.

- 플랜: 이미 구축된 인프라와 새롭게 작성한 환경 구성에 기반하여 구축, 수정, 삭제할 인프라에 대한 실행 계획을 생성합니다.

- 어플라이: 승인 시, 리소스 종속성을 고려하여 테라폼은 제안된 작업을 올바른 순서대로 수행합니다. 예를 들어, VPC의 속성을 수정하고 VPC 안에 있는 가상 머신의 개수를 변경하려고 하면 테라폼은 가상 머신의 규모를 조정하기 전에 먼저 VPC를 다시 만듭니다.

> ### 작성
>
> 환경 구성 파일에서 인프라를 정의합니다.
>> 테라폼 프로젝트 안에 테라폼 환경 구성과 테라폼 스테이트 파일이 위치하게 됩니다.

> ### 플랜
>
> 테라폼이 변경할 인프라를 검토합니다.
>> 테라폼이 어떤 작업을 수행할지 화면에 출력됩니다.

> ### 어플라이
>
> 테라폼이 인프라를 제공하고 스테이트 파일을 업데이트합니다.

## 왜 테라폼을 써야 하나요?

어떻게 테라폼이 인프라의 문제를 해결할 수 있는지 하시코프의 공동 창립자이자 CTO인 아몬 데드가의 설명을 들어 보세요.

[하시코프 테라폼에 대한 아몬 데드가의 소개 영상](https://youtu.be/h970ZBgKINg)

### 어떠한 인프라든 관리할 수 있습니다

> <!-- TODO Link the document below after translating it -->
테라폼은 많은 플랫폼과 서비스를 지원합니다. 여러분이 이미 사용하고 있는 것에 대한 프로바이더를 [테라폼 레지스트리](https://registry.terraform.io/)에서 찾아 보세요. 또한 [본인만의 프로바이더](https://developer.hashicorp.com/terraform/plugin)를 만들 수도 있습니다. 서비스와 인프라를 업그레이드하거나 수정할 때 복잡성을 줄이기 위해, 테라폼은 불변 인프라 방식을 채택했습니다.

### 인프라를 추적할 수 있습니다

테라폼은 인프라를 수정하기 전에 플랜을 생성하고 승인을 받도록 되어 있습니다. 또한 실제 인프라를 스테이트 파일로 추적할 수 있습니다. 스테이트 파일은 여러분이 만든 환경 그 자체를 보여줍니다. 테라폼은 여러분의 환경 구성에 일치시키기 위해 스테이트 파일로 하여금 여러분의 인프라를 어떻게 변경할지 결정합니다.

### 변경을 자동화할 수 있습니다

테라폼의 환경 구성 파일은 선언적이며 인프라의 최종 상태를 나타냅니다. 그리고 테라폼은 기본적인 논리에 기반하고 있어서 여러분은 리소스를 만들기 위한 단계별 지침을 작성하지 않아도 됩니다. 테라폼은 리소스 의존성을 알아내기 위해 리소스 그래프를 그리고 의존성이 없는 리소스들을 병렬적으로 생성하거나 수정합니다.

### 환경 구성을 표준화할 수 있습니다

테라폼은 재사용할 수 있는 구성 요소인 모듈을 지원합니다. 모듈은 인프라의 설정을 변경할 수 있는 집합체를 정의합니다. 모듈을 활용하면 시간을 아낄 수 있으며 모범 사례가 될 수 있습니다. 여러분은 테라폼 레지스트리를 참고하여 공개적으로 이용할 수 있는 모듈을 사용할 수 있고 또는 직접 본인만의 모듈을 작성할 수 있습니다.

### 협업에 유용합니다

<!-- TODO Link the document below after translating it -->
환경 구성이 파일로 작성되기 때문에 여러분은 이것을 버전 관리 시스템(VCS)에 커밋할 수 있습니다. 그리고 팀 간에 테라폼 워크플로를 효율적으로 관리하기 위해 [HCP 테라폼](https://developer.hashicorp.com/terraform/intro/terraform-editions#hcp-terraform)을 사용할 수 있습니다. HCP 테라폼은 일관되고 신뢰할 수 있는 환경에서 테라폼을 실행하며 공유된 스테이트와 비밀 데이터에 대해 안전한 접근, 역할에 따른 접근 제어, 모듈과 프로바이더를 모두 공유하기 위한 개인 소유의 레지스트리 등을 제공합니다.

> #### 팁
>
> <!-- TODO Link the document below after translating it -->
> [테라폼의 사용 사례](https://developer.hashicorp.com/terraform/intro/use-cases)와 [테라폼과 다른 솔루션 비교](https://developer.hashicorp.com/terraform/intro/vs)를 더 알아 보세요.

## 커뮤니티

커뮤니티에 질문하거나 제안하거나 기여해 보세요.

- [하시코프 토론장](https://discuss.hashicorp.com/c/terraform-core/27)에서 질문을 올릴 수 있습니다.

- [기여 안내](https://github.com/hashicorp/terraform/blob/main/.github/CONTRIBUTING.md)를 읽어 보세요.

- [버그나 기능 요청에 관한 이슈](https://github.com/hashicorp/terraform/issues/new/choose)를 올려 주세요.

---

### [테라폼 공식 문서](https://developer.hashicorp.com/terraform/intro)

**마지막 업데이트:** 2025년 2월 3일