# 20210224

## Kotlin의 고차함수(Higher-order Function)

- 매개변수 또는 리턴 값으로 함수를 취하는 함수

```kotlin
fun giveParamAsFun(name: String): String{
	return "Hi, ${name}! Good morning!"
}

// 함수의 argument로 (String) -> String 함수를 포함한다.
fun higerOrder(sayGoodMorning: (String) -> String, name: String, today: Int): String {
	val result = "${sayGoodMorning(name)} Today is ${today}."
    return result
}

fun main(){
	println(higerOrder(::giveParamAsFun, "Dobi", 20210224))
	// Hi, Dobi! Good morning! Today is 20210224
}
```
