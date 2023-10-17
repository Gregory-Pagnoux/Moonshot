# Quality Assurance

## Table of content

- [Quality Assurance](#quality-assurance)
	- [Table of content](#table-of-content)
	- [Test plan](#test-plan)
	- [History of bugs](#history-of-bugs)
		- [Test 1](#test-1)
		- [Test 3](#test-3)

## Test plan

*What is tested, how, and the expected and achieved results ?*

| REFERENCE TEST | ACTION | RESULT EXPECTED | RESULT ACHIEVED |
| :-: | :-: | :-: | :-: |
| 1a | know the state on of the LED | true | **FAIL** |
| b |  |  | **FAIL** |
| c |  |  | **PASS** |
| 2a | set the LED light high or low | true | **PASS** |
| 3a | blink the light | true and false 10 times | **FAIL** |
| b |  |  | **** |
| 4a | Modify the lightness | precentage of light |  |
| 5a | put the light detector in the dark | the brightness of the light increases |  |
| 6a | put the light detector in the daylight | the brightness of the light decreases |  |
| 7a | at a given time, the lights turn on | light on |  |
| 8a | at a given time, the lights turn off | light off |  |
| 9a | turn on all the lights except one (voluntarily turned off) | displays an alert message |  |
| 10a | put voluntarily a high temperature | displays an alert message |  |

## History of bugs

*(refer to the table)*

### Test 1

*last version to the function and test function*

	type LED struct {
		on bool
	}

	func New() *LED {
		l := LED{
		on: false,
		}
		return &l
	}

	// On indicates if the LED is turned on.
	func (l *LED) On() bool {
		return l.on
	}



	func TestOn(t *testing.T) {
		t.Run("false", func(t *testing.T) {
			l := LED{
				on: true,
			}
			want := true
			got := l.On()
			if got != want {
				t.Errorf("The light isn't turn on")
			}
		})
	}

| REFERENCE TEST | TEST REALIZED | EXPLICATION OF THE BUG |
| :-: | :-: | :-: |
| a | when you enter the string `"true"`, the LED blinks and returns `true` | the test didn't return an answer |
| b | when you call the function `l.On()`, return an error if the LED is on | the test return that `l` is undefined |

### Test 3

*last version to the function and test function*

	func (l *LED) Blink() {
		rate := time.Second / 500
		for i := 0; i < 10; i++ {
			l.Set(true)
			time.Sleep(rate)
			l.Set(false)
			time.Sleep(rate)
		}
		return
	}



	func TestBlink(t *testing.T) {
		t.Run("true", func(t *testing.T) {
			l := LED{
				on: true,
			}
			want := true
			got := l.Blink()
			if got != want {
				t.Errorf("The light isn't turn on")
			}
		})
	}

| REFERENCE TEST | TEST REALIZED | EXPLICATION OF THE BUG |
| :-: | :-: | :-: |
| a | call the function `Blink()` and return each `Set()` of the LED | `l.Blink` used as value |
| b |  |  |
