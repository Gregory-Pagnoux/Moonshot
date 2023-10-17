# Quality Assurance

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<details>
<summary>Table of content</summary>

- [Quality Assurance](#quality-assurance)
	- [Test plan](#test-plan)
	- [History of bugs](#history-of-bugs)
		- [Test 1](#test-1)

</details>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## Test plan

*What is tested, how, and the expected and achieved results ?*

| REFERENCE TEST | ACTION | RESULT EXPECTED | RESULT ACHIEVED |
| :-: | :-: | :-: | :-: |
| 1a | know the state on of the LED | true | **FAIL** |
| b |  |  | **PASS** |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

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
