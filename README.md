# watcher-in-lifecycle

This repo is to reproduce the behavior of a zombie watcher in <code>Vue.js</code>.

To test:

- open the console
- click on the `count++` button from CompA a few times and see the logs appear
- toggle to CompB
- click again on the `count++` button from CompB a few times and see that the logs from compA still appear in the console
