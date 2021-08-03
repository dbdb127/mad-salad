# 가계부/금융 앱

사용자의 소비 내역을 시각화, 직관화해주는 가계부/금융 어플리케이션.

## 팀원

김경하, 정이든, 박종회

***

# Web(Client)

### Home

### Auth Validation

##### Sign up

- 이메일과 비밀번호로 회원가입 가능.
- 이메일과 비밀번호 validation check 구현.

##### Login

### History

- 사용자의 거래 내역을 월별로 모두 모아 보여줌.
- 지출과 수입 유형을 구분하여 따로 모아 볼 수 있음.
- 거래 내역을 추가할 수 있음.

### Calendar

- 사용자의 거래 내역을 날짜별로 분류하여 달력에 나타내줌.
- 월별 총 지출 및 수입 금액 확인 가능.
- 수입은 파란색으로, 지출은 빨간색으로 설정하여 유형을 분류함. 
- 각 거래 내역을 클릭하면 상세내역(날짜, 카테고리, 지불 유형, 제목, 금액) 확인 및 수정 가능.
- Add History 버튼을 통해 거래 내역을 추가할 수 있음.

### Analytics

- By Categoreis: 사용자의 소비를 파이 그래프와 막대 그래프를 이용해, 카테고리로 나눠 비교 분석함.
- By Dates: 사용자의 소비를 꺽은선 그래프를 이용해, 날짜별로 비교 분석함.

### Payment Management

- 사용자의 계좌(거래 수단)을 관리함.
- 계좌를 추가하고 제거할 수 있음.
- 사용자가 관리한 계좌를 거래 추가/수정 시 사용할 수 있음.

***
# Server

## Tech
* Nodejs
* TypeScript
* Express
* Prisma(ORM)

## DB schema
Mysql database schema

## REST API 

[Auth](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/routes/auth.ts#L2)

- [x] [Login (jwt)](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/AuthController.ts#L11)
- [x] [Change password](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/AuthController.ts#L68)


[User](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/routes/user.ts#L1)

- [x] [Join (Sign up)](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/UserController.ts#L22 )
- [x] [Unroll](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/UserController.ts#L88)

[Account](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/routes/acct.ts#L1)

- [x] [Create Account](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/AccountController.ts#L10)
- [x] [Delete Account](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/AccountController.ts#L49)
- [x] [Get All Accounts](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/AccountController.ts#L92)  

[Transaction](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/routes/transaction.ts#L1)

- [x] [Income](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/TransactionController.ts#L13)
- [x] [Expenditure](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/TransactionController.ts#L124) 
- [x] [Send](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/TransactionController.ts#L240) 
- [x] [Update transaciton](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/TransactionController.ts#L423)
- [x] [Delete Ttransaction](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/TransactionController.ts#L512) 
- [x] [Show history by month](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/TransactionController.ts#L545)
- [x] [Show history by month grouped by history](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/TransactionController.ts#L604)  
- [x] [Show history by month grouped by created date](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/TransactionController.ts#L676)
- [x] [Get pending Transactions which are in the state right before sending and receiving money](https://github.com/kaist-madcamp/mad-salad/blob/ef365b370ed164f784bc36fce5d99d9b68cfce16/server/src/controllers/TransactionController.ts#L874)  

[Category](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/routes/category.ts#L1)

- [x] [Get all categories](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/CategoryController.ts#L9)
- [x] [Get all expenditure categories](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/CategoryController.ts#L32)
- [x] [Get all income categories](https://github.com/kaist-madcamp/Week3-finance-app/blob/5f0409d62bb17e4452f7b96178cfa9bd7d5f9dc6/server/src/controllers/CategoryController.ts#L58)  
