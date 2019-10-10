# JavaScript
## [변수]
새로운 변수는 let, const, var 키워드로 선언됩니다.
	• let : 블록 유효 범위 변수를 선언
ex) for(let var =0; var<5; var++){
// var은 이곳에서만 유효
}
// for 문 밖에서 var은 유효X
	• const : 값이 변경되지 않는 변수 선언
	• var : 가장 일반적인 변수 선언


## [객체]
JS객체는 이름 - 값 쌍의 모임
—> 값 : 객체를 포함하여 아무 js값이 될 수 있음.
—> 이름 : 무.조.건. 문자열만

빈 객체 생성방법
ex1) var obj = new Object();
ex2) var obj = {}; //객체 리터럴 구문 -> JSON 구문의 핵심

이 때 객체의 속성에 접근하는 방법
	1. obj.name
	2. obj[name]

객체 리터럴 구문으로 객체의 전체적인 구조를 초기화 할 수도 있음~!
var obj = {
    name: "Carrot",
    "for": "Max",
    details: {
        color: "orange",
        size: 12
    }
}

이 경우
obj.details.size || obj[details][size] 일케 접근할 수 있슈


## [배열]
일반 객체와 비슷하지만 length 속성을 사용 가능
하지만~! length == 최대 인덱스 + 1
	• concat : 해당 배열에 지정한 항목들을 추가한 새로운 배열을 돌려줌
	• pop : 마지막 항목을 제거한 다음 돌려둠
	• push : 마지막에 하나 이상의 항목을 추가
	• slice : 배열의 일부분을 돌려줌
	• sort : 비교에 사용할 함수를 따로 지정 가능
	• splice : 구역을 삭제하거나 항목을 추가해서 배열을 수정할 수 있음
	• unshift : 배열의 시작부분에 항목을 붙일 수 있음


## [함수]
함수 내에서 매개변수로 넘겨진 모든 값을 가지고 배열과 비슷한 객체인 arguments로 접근할 수 있음
ex)
function add() {
    var sum = 0;
    for (var i = 0, j = arguments.length; i < j; i++) {
        sum += arguments[i];
    }
    return sum;
}

add(2, 3, 4, 5)

————————————————————————————————————————
function avg() {
    var sum = 0;
    for (var i = 0, j = arguments.length; i < j; i++) {
        sum += arguments[i];
    }
    return sum / arguments.length;
}
> avg(2, 3, 4, 5)

어라아! avg함수에 배열을 매개변수로 넣고 싶은 거얼~

function avgArray(arr) {
    var sum = 0;
    for (var i = 0, j = arr.length; i < j; i++) {
        sum += arr[i];
    }
    return sum / arr.length;
}
> avgArray([2, 3, 4, 5])

함수를 하나 더 만들면 뭔가… 거시기 하지 않나아~


이럴 땐!
> 만든 함수 재사용 -> apply() 메소드 사용

avg.apply(null, [2, 3, 4, 5])
> 두번째 매개변수 == ‘매개변수들’로 사용하고자 하는 배열

————————————————————————————————————————
***익명의 함수를 만들어 보자~***
의미적으로 function avg()와 형식은 같삼~

BUT! : 문장의 어느 곳에나 일반적인 방식으로 완전한 함수 정의를 넣을 수 있도록 허용하는 것이기 때문에 매우 강력
이라는데 아직 잘 이해는 안 된다

var avg = function() {
    var sum = 0;
    for (var i = 0, j = arguments.length; i < j; i++) {
        sum += arguments[i];
    }
    return sum / arguments.length;
}

+ arguments.callee는 현재 함수이고 모든 함수는 객체


————————————————————————————————————————
	• 사용자 정의 객체

function makePerson(first, last) {
    return {
        first: first,
        last: last,
        fullName: function() {
            return this.first + ' ' + this.last; //this :: 현재 객체 참조
        },
        fullNameReversed: function() {
            return this.last + ', ' + this.first;
        }
    }
}
> s = makePerson("Simon", "Willison")
> s.fullName() // print :: Simon Willison
> s.fullNameReversed() //print :: Willison, Simon