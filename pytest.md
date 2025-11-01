# can't run test on list of fixtures

https://github.com/pytest-dev/pytest/issues/349

``` python
@pytest.fixture
def foo():
    return 456

@pytest.fixture
def bar():
    return 123

# doesn't work
@pytest.mark.parametrize('arg0', [foo, bar])
def test_something(arg0):
    assert arg0 in (123, 456)
# doesn't work either
@pytest.mark.parametrize('arg0', ['foo', 'bar'], indirect=True)
def test_something(arg0):
    assert arg0 in (123, 456)

```

one solution

``` python
# wtf is this garbage
@pytest.fixture
def choice(request):
    if request.param == "foo":
        return 456
    elif request.param == "bar":
        return 123

@pytest.mark.parametrize('choice', ['foo', 'bar'], indirect=True)
def test_something(choice):
    assert choice in (123, 456)

```

# no way to handle really long fixtures

``` python

@pytext.fixture
def a_really_long_fixture_name():
    return 123
    
# doesn't work
def test_foo(short=a_really_long_fixture_name):
    assert short == 123, "fail"

# this does, but is ugly
def test_foo(a_really_long_fixture_name):
    short = a_really_long_fixture_name
    assert short == 123, "fail"
```