# kalliope-repeat

A neuron to say / repeat text


## Synopsis

Make kalliope say what you want

## Installation

  ```
  kalliope install --git-url https://github.com/bacardi55/kalliope-repeat.git
  ```


## Options

| parameter  | required | default   | choices  | comment                                                                                    |
|------------|----------|-----------|----------|--------------------------------------------------------------------------------------------|
| *          | Yes      |           | String* * | Your incoming query                                                                        |


You can put as many parameters that you want, the neurons will simply send them back to you.
So for example you send arg1 and arg2, you will be able to use {{arg1}} and {{arg2}} in your say_template or template.


## Return Values

| Name                | Description                                                                           | Type     | sample   |
| ------------------- | ------------------------------------------------------------------------------------- | -------- | -------- |
| *                   | The query you sent                                                                    | String   |          |

As describe above, return values are all the input values.


## Synapses example

Play a playlist by giving its name to kalliope

```yaml
  - name: "Repeat"
    signals:
      - order: "repeat after me {{ query }}"
    neurons:
      - repeat:
          query: "{{query}}"
          say_template:
            - "{{ query }}"
```

```yaml
  - name: "Say-hello-to"
    signals:
      - order: "say hi to {{ name }}"
    neurons:
      - repeat:
          name: "{{name}}"
          say_template:
            - "Hi {{ name }}, and welcome"
```

```yaml
  - name: "Repeat-via-api"
    signals:
      - order: "api-repeat-cmd {{ query }}"
    neurons:
      - repeat:
          query: "{{query}}"
          say_template:
            - "{{ query }}"
```

## Template example



see more example in the [sample brain file](https://github.com/bacardi55/kalliope-repeat/blob/master/samples/brain.yml)

* [An example of use of thie neuron](http://bacardi55.org/2017/02/16/kalliope-acting-as-a-reminder.html)
* [my posts about kalliope](http://bacardi55.org/kalliope.html)

