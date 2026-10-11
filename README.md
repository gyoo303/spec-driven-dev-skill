# Spec-Driven Development Skill

Claude Code용 Spec-Driven Development 스킬입니다. 코딩 전에 체계적인 문서화를 통해 개발을 진행합니다.

## 워크플로우

```
Feature Request → Requirements → Design → Tasks → Implementation
                     ↓              ↓        ↓
              requirements.md  design.md  tasks.md
```

## 설치 방법

### 전역 설치 (모든 프로젝트에서 사용)

```bash
git clone https://github.com/YOUR_USERNAME/spec-driven-dev-skill.git
mkdir -p ~/.claude/skills
cp -r spec-driven-dev-skill/* ~/.claude/skills/
```

### 프로젝트별 설치

```bash
cd /your/project
mkdir -p .claude/skills
git clone https://github.com/YOUR_USERNAME/spec-driven-dev-skill.git
cp -r spec-driven-dev-skill/* .claude/skills/
```

## 사용 방법

Claude Code에서 다음과 같이 요청하세요:

- "새 프로젝트를 spec-driven으로 진행하자"
- "요구사항 정리해줘"
- "design document 만들어줘"
- "task breakdown 해줘"

## 3단계 프로세스

### Phase 1: Requirements Analysis
- 사용자 스토리 작성
- EARS 표기법 기반 인수 조건
- 비기능 요구사항 정의

### Phase 2: Technical Design
- 시스템 아키텍처
- 기술 스택 결정
- API 명세
- 데이터 모델

### Phase 3: Task Implementation
- 의존성 기반 태스크 정렬
- 요구사항 ID 연결
- 상태 추적

## 파일 구조

```
.
├── SKILL.md                    # 스킬 정의
├── spec-driven-dev.skill       # 스킬 메타데이터
└── references/
    ├── requirements-template.md
    ├── design-template.md
    └── tasks-template.md
```

## 라이선스

MIT
