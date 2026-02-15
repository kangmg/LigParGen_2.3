# LigParGen 2.3

ORCA 계산 결과로부터 OPLS-AA/CM5 force field 파라미터를 생성한다. 여러 conformer의 ORCA output을 입력하면 Boltzmann averaging으로 CM5 전하를 계산한다. 최신 Python 패키지(networkx, pandas, numpy 등)와의 호환성을 위해 deprecated API를 수정하였다.

출력 포맷: OpenMM, CHARMM, GROMACS, LAMMPS, TINKER, Desmond, Q, PDB2PQR, MCPRO/BOSS

## 환경변수

```bash
export BOSSdir=/path/to/BOSS
```

## 사용법

단일 conformer:

```bash
LigParGen -q output.out -r RES -c 0 -o 0
```

여러 conformer (Boltzmann averaging):

```bash
LigParGen -q /path/to/conf_*/output.out -r RES -c 0 -o 0
```

| 옵션 | 설명 |
|------|------|
| `-q` | ORCA log 파일 경로 (glob 패턴 가능) |
| `-r` | residue 이름 (3자) |
| `-c` | 분자 전하 |
| `-o` | 최적화 수준 (ORCA 사용 시 0 고정) |

결과는 현재 디렉토리에 `RES.zip`으로 저장된다.
