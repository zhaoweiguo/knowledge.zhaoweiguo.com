.. _sphinx-normal-code:

代码
####

基本
====

1.局部代码格式:

``usage.rst``

2.段落代码格式:

代码段格式::

    xxxx xxx xxx

3.另一种代码格式(高亮3,5行)::

    .. code-block:: erlang
       :linenos:
       :emphasize-lines: 3,5
       :dedent: 4

            -module(abc).
            -export([ex/0]).

            ex() ->
                Ex="dedent=4可以去除每一行的前4个字符".


.. code-block:: erlang
   :linenos:
   :emphasize-lines: 3,5
   :dedent: 4

        -module(abc).
        -export([ex/0]).

        ex() ->
            Ex="dedent=4可以去除每一行的前4个字符".




指定显示从哪一行开始::

    .. code-block:: ruby
       :lineno-start: 10

       Some more Ruby code, 
       with line numbering starting 
       at 10.

.. code-block:: ruby
   :lineno-start: 10

   Some more Ruby code, 
   with line numbering starting 
   at 10.

multiple code examples::

    # 配置增加
    extensions = ['sphinx.ext.autosectionlabel',
              'sphinxcontrib.osexample']

    .. example-code::

      .. code-block:: JSON

        {
          "key": "value"
        }

      .. code-block:: python

        pygments_style = 'sphinx'


      .. code-block:: ruby

        print "Hello, World!\n"


    🛑说明: 好像不生效了(应该需要插件吧，不常用，不记得和怎么操作了)


.. .. example-code::

..   .. code-block:: JSON

..     {
..       "key": "value"
..     }

..   .. code-block:: python

..     pygments_style = 'sphinx'


..   .. code-block:: ruby

..     print "Hello, World!\n"




全局
====

功能::

    1. 为行数超过5行的自动显示行数
    即使不加:linenos:或:lineno-start:标签也显示行数
    2. 默认一直使用console语法高亮直到遇到下一个highlight

.. highlight:: console
    :linenothreshold: 5

不指定显示行数则不显示:

.. code-block::

    echo "1"
    echo "1"

指定显示行数则显示:

.. code-block::
    :linenos:

    echo "1"
    echo "1"

超过5行的，不指定显示行数也会显示:

.. code-block:: python
   :emphasize-lines: 3,5

   def some_function():
       interesting = False
       print 'This line is highlighted.'
       print 'This one is not...'
       print '...but this one is.'







