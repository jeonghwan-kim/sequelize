# Sequelize ORM Study

### Sequelize + Express.js
[Usage for Express.js](http://docs.sequelizejs.com/en/1.7.0/articles/express/)

models 폴더에 데이터베이스 로직 관련 파일을 저장함.

models 폴더
* model/index.js: 폴더내 모델들을 로딩
* model/user.js: sequelize.define(), 모델 정의, Task 모델과 1:n 관계 설정
* model/task.js: 상동 

routes 폴더로 라우팅.

라우팅시 models.User.findAll() 함수로 데이터베이스 조회 

### Installation
http://docs.sequelizejs.com/en/1.7.0/docs/installation/

```$ npm install sequelize --save```

```var Sequelize = require(‘sequelize’);```

### Usage
http://docs.sequelizejs.com/en/1.7.0/docs/usage/

데이터베이스 연결 

다양한 연결 옵션 가능

Mysql 쿼리를 직접 실행할 수 있음

### Models
http://docs.sequelizejs.com/en/1.7.0/docs/models/

모델은 자바스크립트 객체로서 데이터베이스 테이블과 연동되는 개념

```javascript
var Project = sequelize.define('Project', {
  title: Sequelize.STRING,
  description: Sequelize.TEXT
});
```

컬럼 옵션을 지정할 수 있다. 

데이터 타입은 [여기](http://docs.sequelizejs.com/en/1.7.0/docs/models/#data-types)에서 확인

```
Project.find(123): id로 검색
Project.find({ where: {title: ‘aProject’} }): where 조건절로 검색
Project.findOrCreate(): 조회후 없으면 생성 
...
```

### Instance
http://docs.sequelizejs.com/en/1.7.0/docs/instances/

```javascript
var project = Project.build(); // 모델을 이용해 자바스크립트 인스턴스 생성
project.save(); // 저장 
```

Project.create()는 뭐가 다른가? [여길](http://nodeqa.com/nodejs_ref/30#SU5TRVJUICMy) 보자

CRUD 모두 가능함

벌크로도 작업 가능함

increment / decrement는 뭐지?

### Associations
http://docs.sequelizejs.com/en/1.7.0/docs/associations/


###  Migrations
커맨드라인툴 설치: ```npm install sequelize-cli```

마이그레이션 생성:```sequelize migration:create ```

마이그레이션 실행(up): ```sequelize db:migrate```

마이그레이션 취소(down): ```sequlize db:migrate:undo```

### Reference
* [Sequalize + Express.js](http://docs.sequelizejs.com/en/1.7.0/articles/express/)
* [Sequelize #1 개념과 CRUD](http://nodeqa.com/nodejs_ref/30)
* [Sequelize #2 Association](http://nodeqa.com/nodejs_ref/31)
* [sequelize #3 Migration](http://nodeqa.com/nodejs_ref/32)

