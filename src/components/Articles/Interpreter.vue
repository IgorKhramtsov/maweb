<template>
  <Article title="Simple interpreter" year="2019" repoUrl="http://github.com/IgorKhramtsov/interpreter">
    <p class="col-md-10">
      In university, at end of "Linguistic analysis" discipline, I have developed a simple
      interpreter of C-like language. First of all, were designed diagrams for lexical and
      syntax parsers, semantic analyzer, and process of building semantic tree.
      With all these diagrams I, start implementing all of this in C++.
    </p>
    <div class="col-md-10">
      <MacOsWindow title="Interpreter">
        <img
          src='../../assets/interpreter.gif'
          alt="Interpreter"
          class="gif"
        >
      </MacOsWindow>
    </div>
    <p class="col-md-10">
      Designed language interpreter support
      <ul>
        <li> Types (int, bool, void for functions) </li>
        <li> Two-dimensional arrays (also int, bool) </li>
        <li> Functions with arguments (with overloading) </li>
        <li> Scopes, «if» statements </li>
        <li> Logical operators (&lt;, &gt;, &lt;=, &gt;=, ==, !=) </li>
        <li> Basic math operators (+, -, /, *, %) </li>
        <li> Assignment with math operator (+=, -=, etc) </li>
        <li> Increment/decrement (--, ++) </li>
        <li> Multiple declaration on one line </li>
      </ul>
    </p>
    <p class="col-md-10">
      Interpreter was developed to understand the process of linguistic analysis of modern
      programming language, and have some architectural issues.
    </p>
  </Article>
</template>

<script>
import MacOsWindow from '../MacOsWindow.vue';
import Article from '../Article.vue';

export default {
  name: 'Interpreter',
  components: {
    MacOsWindow,
    Article,
  },
};
</script>

<style lang="scss" scoped>
.gif {
  width: 100%;
  margin-bottom: -1px;
}
</style>
