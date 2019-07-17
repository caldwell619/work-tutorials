# Getting Started With Vue CLI Testing

This quick guide will help you get started testing Vue Single File Components ( commonly called SFC).

## Who this is for

This guide assumes very basic knowledge of Vue, with little to no knowledge of Webpack, Babel and other JS scaffolding tools. This also assumes Jest syntax will be used.

## Setup

A lot of the work will be handled by the Vue CLI. Ensure that you've globally installed Vue, as you will not be able to run the commands without it.

If you haven't setup the scaffolding yet, check out [this official guide](https://cli.vuejs.org/guide/).

### Steps

The steps to get a project running are really simple.

- Locate a directory you want the project to live, and run `vue create PROJECT_NAME`
- Choose the default option, `babel, eslint`.
- Wait <= lol, it takes a hot minute

Once this has completed you have, a running Vue project. Congrats.

## Setting up testing

This part becomes a little more ambiguous. The [official docs](https://vuejs.org/v2/guide/unit-testing.html) state that the CLI has built in testing, but it doesn't. Kinda. It's weird. Leave me alone.

There is no `test` command in the scripts. So to me, that means it's not built in. I haven't personally found a way to test with **only** the `vue create` scaffolding.

To "fix" this, we'll add the [Vue Test Utils](https://vue-test-utils.vuejs.org/). The problem with their documentation ( in my most humblest of opinions ) is that they don't tell you how to actually run the tests. It's assumed you already know what you're doing, when I certainly do not.

How dare they assume my competency.

### Steps

Here will install the test utils.

- **Inside of PROJECT_NAME/**, run `vue add @vue/cli-plugin-unit-jest`.

This will make several changes to the files needed to run the tests successfully.

- Run `npm run test:unit` to test the pre-built test this command provided.

You'll notice ( if you're paying attention ), that this `test:unit` command is new. The cli plugin was added, and it added the file, `jest.config.js` that we need to run them successfully.

### Caveats

A couple side notes from my frustrating experiences that lead to the creation of this fine piece of literature.

- The newest version of `babel-jest` is 24.x.x. This **will** break your tests.

  - If you install these independently like yours truly, make sure you revert to 23.6.x

- This configuration will **not** pick up on `file.test.js`, they need to be `file.spec.js`

## Testing

The docs shine here, so feel free to [check them out](https://vuejs.org/v2/guide/unit-testing.html) or have a look at this [great video](https://www.youtube.com/watch?v=vQ4A7EfAHOg)

- The video is outdated, but the actual testing procedures are where it's at.

### My take on tests

You've made it this far, so I feel confident that you don't find this totally worthless. With that in mind, here's my quick how to on the procedural aspect of testing

### Making a test

The test they included is great. It shows every aspect of testing to give you a glimpse into how to do it.

Buuuuuuut, what if you're like me and have no idea what's happening? I got you, fam.

#### Describe

- Start by making a new `describe()` function.
- This is the root of your test, it describes the series of tests you're going to be doing.

The `describe()` function takes 2 arguments.

1. The name of your group of tests - `string`
2. The meat of your tests - `function`
   - This function can be named or anonymous

So far we have:

```javascript
describe('Intro Tests', () => {});
```

Cool. So now we need to make actual tests.

#### Test

Try to think logically ( it's hard, I know ) when grouping tests. Don't be afraid to make multiple describes, and group them accordingly.

- Tests are structured similarly to the `describe()` function.
- They both accept a string and a function as arguments
- The string will describe the individual test expectations
  - eg: `'2 + 2 = 4'`

So far we have:

```javascript
describe('Intro Tests', () => {
	test('I will be a famous rapper', () => {});
});
```

### Expect

He we have the actually 'test' part of the whole test conceptual sandwich

- `expect()` is a function that must return a boolean.
- `expect()` has many chaining methods attached to it, for example `.toBe()`
  - These methods work as comparison operators. You can also compare primitive data types as you normally would, these options just extend the capabilities of `===` and `==`
  - I could go on and on, but the [docs](https://jestjs.io/docs/en/expect) are infinitely better than my rambling

So here is our actual "test". We expect something to be something else. Weird..

So to finish off the test:

```javascript
describe('Intro Tests', () => {
    test('I will be a famous rapper', () => {
        const successful = 'successful
        expect('rap career').toBe(successful)
    })
})
```

This would clearly fail, as have I in my rap career. I'm more of a fan, than a performer.

- To actually run the test, execute `npm run test:unit`, which will scrape our entire codebase looking for `.spec.js` file extensions.

To fix this, we need to actually compare 2 like values:

```javascript
describe('Intro Tests', () => {
	test('I will be a famous rapper', () => {
		const successful = false;
		expect(successful).toBe(false);
	});
});
```

Yay!

## Testing Single File Components

The above is gold, trust me. However, we need to test a little more. Such as components..

To do this, we need 2 things.

1. The `shallowMount` or `mount` functions from `@vue/test-utils`
   - There's a good answer [here](https://stackoverflow.com/questions/53225300/the-difference-between-vue-test-utils-mount-and-shallowmount) on the difference
2. The component we're testing. Duh..

So in our test file, we destructure the `shallowMount`, and import the component like normal:

```javascript
import { shallowMount } from '@vue/test-utils
import Component from '@/components/COMPONENT_NAME'
```

The `@` just searches through the folder structure looking for the `components/` directory. An example of this is already given in the pre-built test, but sometimes not everyone knows what's going on.

### Testing the component

So now that we have the necessary tools, we need to implement them.

- Make a constant named `wrapper`, containing the mounted component
  - `const wrapper = shallowMount(Component);`
- The makes a testable version of your component, as if it were actually mounted in the DOM.
- `wrapper` is convention, so remember to change if necessary, but try to keep it as such for readability.

Now `wrapper` has a bunch of properties ( `wrapper` is an object ) that can be found [here](https://vue-test-utils.vuejs.org/api/wrapper/#properties).

The docs are great at specifics, but tying them together ( in my opinion ).

Here you can go nuts and test whatever your little heart desires. These are done inside of the `expect()` function.

### Testing if you are testing correctly

It's always a good idea to check to see if you're on the correct planet before spending a bunch of time writing and thinking.

To see if you've imported and mounted correctly, start with `expect(wrapper.isVueInstance)`. This will return a pass is it actually is.

## Final Thoughts

Hopefully this didn't suck.
