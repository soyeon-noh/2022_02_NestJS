# NestJS Study Start

---

with https://docs.nestjs.com/
startAt : 2022.02.26

# 설치 및 프로젝트 생성

nest CLI 를 사용하여 프로젝트 디렉토리를 생성한다
`npm i -g @nestjs/cli`
`nest new project-name`

`nest g module user`

# 기본구조

srs

- app.controller.ts : 단일 경로(route)가 있는 기본 컨트롤러
- app.controller.spec.ts : 컨토를러에 대한 단위 테스트
- app.module.ts : 애플리케이션의 루트 모듈
- app.service.ts : 단일 메서드를 사용하는 기본 서비스
- main.ts : 핵심 함수 `NestFactory` 를 사용하여 Nest 응용 프로그램 인스턴스를 만드는 응용 프로그램의 항목 파일

## Controller

- 컨트롤러는 들어오는 요청(request)를 처리하고 클라이언트에 응답(rresponse)을 반환하는 역할

### Routing

- `@Controller` : 기본 컨트롤러를 정의하는 데 필요한 데코레이터(decorator)
- `@Controller('cats')` : '/cats' 라는 path를 prefix로 지정하여 보다 편리하게 작성할 수 있다.
- @Get() : HTTP request method 중 Get을 사용하겠다는 decorator. '/cats' 뒤에 올 route path 를 추가할 수 있다.

```typescript
import { Controller, Get } from "@nestjs/common";

@Controller("cats")
export class CatsController {
  @Get()
  findAll(): string {
    return "This action returns call cats";
  }
  @Get(:id)
  findOne(@Param('id') id: string){
      return "This action returns call a cat";
  }
}
```
