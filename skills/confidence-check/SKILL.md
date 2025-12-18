# Confidence Check Skill

구현 전 신뢰도 평가 프레임워크입니다. 작업을 시작하기 전에 ≥90% 신뢰도를 요구합니다.

## 개요

잘못된 방향의 작업을 방지하기 위해 구현 전에 신뢰도를 평가합니다.

**토큰 예산**: 100-200 토큰
**ROI**: 잘못된 방향 중단 시 25-250배 토큰 절약

**테스트 결과 (2025-10-21)**:
- Precision: 1.000 (false positive 없음)
- Recall: 1.000 (false negative 없음)
- 8/8 테스트 케이스 통과

## 5가지 평가 기준

| 기준 | 가중치 | 설명 |
|------|--------|------|
| 중복 구현 없음 | 25% | grep/glob으로 기존 기능 검색 |
| 아키텍처 준수 | 25% | 기존 기술 스택(Supabase, UV, pytest) 확인 |
| 공식 문서 확인 | 20% | Context7 MCP, WebFetch로 공식 문서 검토 |
| OSS 참조 | 15% | GitHub에서 작동하는 예제 찾기 |
| 근본 원인 식별 | 15% | 에러 메시지와 로그를 통한 원인 분석 |

## 의사결정 프레임워크

| 점수 | 행동 |
|------|------|
| ≥0.90 (90% 이상) | ✅ 구현 진행 |
| 0.70-0.89 (70-89%) | ⚠️ 대안 제시 및 명확화 질문 |
| <0.70 (70% 미만) | ❌ 중단하고 추가 컨텍스트 요청 |

## 신뢰도 수준

### High (≥90%)
- 근본 원인 식별됨
- 솔루션 검증됨
- 중복 없음
- 아키텍처 준수

### Medium (70-89%)
- 여러 접근 방식 가능
- 트레이드오프 고려 필요

### Low (<70%)
- 조사 미완료
- 근본 원인 불명확
- 공식 문서 미확인

## 사용 방법

```python
from confidence import ConfidenceChecker

checker = ConfidenceChecker()
context = {
    "task": "새 기능 구현",
    "duplicate_check_complete": True,
    "architecture_check_complete": True,
    "official_docs_verified": True,
    "oss_reference_complete": True,
    "root_cause_identified": True
}

score = checker.assess(context)
recommendation = checker.get_recommendation(score)
print(f"신뢰도: {score:.0%}")
print(recommendation)
```

## ROI 가치

100-200 토큰의 신뢰도 검사 투자로 잘못된 방향의 작업을 방지하여 5,000-50,000 토큰을 절약할 수 있습니다.
