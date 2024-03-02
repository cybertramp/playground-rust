

### installation

```bash
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh

rustc --version
rustc 1.76.0 (07dca489a 2024-02-04)

echo $PATH | grep cargo
rustup update

```



### rust 이해

- Rust는 `{}` 중괄호 필수

- tab 안쓰고 space 4칸 기본

- `!` 는 macro

- 실행하는 건 rustc -> go 랑 비슷

- Rust 언어는 AOT(ahead-of-time) 컴파일 언어
  (반대는 JIT)

  > JIT vs AoT차이
  >
  > JIT는 프로그램 실행중에 컴파일을 수행하여 실행
  > 빠른 개발/배포, 빌드 시간 단축
  >
  > AoT는 프로그램 실행전에 컴파일을 수행하고 실행
  > 빠른 실행 속도, 빌드 시간 증가, 배포 파일 크기 증가



### Cargo

- Rust 패키지 관리 툴

- toml format 사용

  > Python과 유사

#### Usage

```bash
# check cargo installed
cargo --version

# create cargo project
cargo new <direcotory 명>
# create cargo project with git
cargo new --vcs=git <directory 명>
```



#### cargo toml

```toml
[package]
name = "hello_cargo_git"
version = "0.1.0"
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]

```

**[package]**에 패키지에 대한 정보들이 기록되며, **[dependencies]**에 해당 패키지에 필요한 의존 패키지들이 기록

#### build & run

```shell
cd <project>

# build
cargo build

# Run
cargo run

# check build(Not create excutable files)
cargo check

# build with release
cargo build --release
```

- 빌드시 기본으로 unoptimized, debuginfo 옵션으로 빌드가 진행

- python과 유사하게 Cargo.lock 파일이 생성되며, 빌드된 내용들에 대한 의존성에 대한 버전 정보가 기록됨

- 빌드로 만들어지 파일은 `target/debug`에 생성
- 릴리즈 옵션인 경우 `target/release`에 생성
- 운영체제에 따라 명령이 다르지 않음
  go와 다른 부분





