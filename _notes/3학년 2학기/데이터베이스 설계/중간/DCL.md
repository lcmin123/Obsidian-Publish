**제약조건**

**Constraint**
–Database 테이블레벨에서특정한규칙을설정해둠
–예상치못한데이터의손실이나일관성을어기는데이터의추가, 변경등을예방함

종류
–**NOT NULL**
	–NULL 값이들어올수없음
	–컬럼형태로만제약조건정의할수있음(테이블제약조건불가)
	
–**UNIQUE** 
	–중복된값을허용하지않음(NULL은들어올수있음)
	–복합컬럼에대해서도정의가능
	–자동적으로인덱스생성
	
–**PRIMARY KEY**
	–NOT NULL + UNIQUE (인덱스자동생성)
	–테이블당하나만나올수있음
	–복합컬럼에대해서정의가능(**순서중요!**)
	
–**FOREIGN KEY**
	–**참조무결성**제약
	–일반적으로REFERENCE 테이블의PK를참조
	–REFERENCE 테이블에없는값은삽입불가
	–REFERENCE 테이블의레코드삭제시동작
		•**ON DELETE CASCADE**: 해당하는FK를가진참조행도삭제
		•**ON DELETE SET NULL**: 해당하는FK를NULL로바꿈
		
–**CHECK**
	–임의의조건검사
	–조건식이참이어야변경가능
	–동일테이블의컬럼만이용가능

  

제약조건추가
–**ALTER TABLE**테이블이름**ADD CONSTRAINT**…
–NOT NULL은추가못함

**ALTER TABLE emp ADD CONSTRAINTemp_mgr_fk**
**FOREIGN KEY(mgr)REFERENCES emp(empno);**

제약조건삭제
–**ALTER TABLE** 테이블이름**DROP CONSTRAINT** 제약조건이름
–PRIMARY KEY의경우FK 조건이걸린경우에는CASCADE로삭제해야함

**ALTER TABLE book DROP CONSTRAINTc_emp_u;**
**ALTER TABLE dept DROP PRIMARY KEY CASCADE;**
  