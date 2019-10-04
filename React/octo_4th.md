# React Hooks

## useEffect는 무엇일까요?
useEffect는 리액트 컴포넌트가 <b>랜더링 될 때마다</b> 특정 작업을 수행하도록 설정 할 수 있는 Hook입니다.
ex)
```javascript
useEffect(() => {
    console.log('렌더링이 되었습니다.');
});
```

## 처음 렌더링 될 때만(마운트 될 때만) 실행시키고 싶을 경우
함수의 두번째 파라미터로 비어있는 배열을 넣어주면 됩니다.
ex)
```javascript
 useEffect(() => {
    console.log('처음 렌더링 될 때만 실행됩니다.');
  }, []);
```

## 특정 값이 업데이트 될 때만 실행하고 싶을 때
useEffect의 두번째 파라미터로 전달되는 배열 안에 검사하고 싶은 값을 넣어주면 됩니다!
ex)
```javascript
  useEffect(() => {
    console.log(name);
  }, [name]);
```
### useEffect 정리
useEffect는 렌더링 되고난 직후 항상 실행되며, 두번째 파라미터 배열에 무엇을 넣느냐에 따라 실행 조건이 달라집니다.
컴포넌트가 업데이트 되기 전 작업을 수행하고 싶다면 cleanup 함수를 반환해주어야 합니다.
ex)
```javascript
  useEffect(() => {
    console.log('렌더링이 되었습니다.');
    return () => {
        console.log("뒷정리, cleanup이 되었습니다.");
    };
  });
```
렌더링이 되었다면
"렌더링이 되었습니다."가 출력 후
"뒷정리, cleanup이 되었습니다."가 출력될 것입니다.

//내일은 useContext를 정리 할 예정입니다~.~