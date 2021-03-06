.. index::
   single: Forms; Fields; LanguageType

LanguageType Field
==================

The ``LanguageType`` is a subset of the ``ChoiceType`` that allows the
user to select from a large list of languages. As an added bonus, the language
names are displayed in the language of the user.

The "value" for each language is the *Unicode language identifier* used
in the `International Components for Unicode`_ (e.g. ``fr`` or ``zh_Hant``).

.. note::

    The locale of your user is guessed using :phpmethod:`Locale::getDefault`,
    which requires the ``intl`` PHP extension to be installed and enabled.

Unlike the ``ChoiceType``, you don't need to specify a ``choices`` option as the
field type automatically uses a large list of languages. You *can* specify the option
manually, but then you should just use the ``ChoiceType`` directly.

+-------------+------------------------------------------------------------------------+
| Rendered as | can be various tags (see :ref:`forms-reference-choice-tags`)           |
+-------------+------------------------------------------------------------------------+
| Options     | - `alpha3`_                                                            |
|             | - `choice_translation_locale`_                                         |
+-------------+------------------------------------------------------------------------+
| Overridden  | - `choices`_                                                           |
| options     |                                                                        |
+-------------+------------------------------------------------------------------------+
| Inherited   | from the :doc:`ChoiceType </reference/forms/types/choice>`             |
| options     |                                                                        |
|             | - `error_bubbling`_                                                    |
|             | - `error_mapping`_                                                     |
|             | - `expanded`_                                                          |
|             | - `multiple`_                                                          |
|             | - `placeholder`_                                                       |
|             | - `preferred_choices`_                                                 |
|             | - `trim`_                                                              |
|             |                                                                        |
|             | from the :doc:`FormType </reference/forms/types/form>`                 |
|             |                                                                        |
|             | - `attr`_                                                              |
|             | - `data`_                                                              |
|             | - `disabled`_                                                          |
|             | - `empty_data`_                                                        |
|             | - `help`_                                                              |
|             | - `help_attr`_                                                         |
|             | - `help_html`_                                                         |
|             | - `label`_                                                             |
|             | - `label_attr`_                                                        |
|             | - `label_format`_                                                      |
|             | - `mapped`_                                                            |
|             | - `required`_                                                          |
|             | - `row_attr`_                                                          |
+-------------+------------------------------------------------------------------------+
| Parent type | :doc:`ChoiceType </reference/forms/types/choice>`                      |
+-------------+------------------------------------------------------------------------+
| Class       | :class:`Symfony\\Component\\Form\\Extension\\Core\\Type\\LanguageType` |
+-------------+------------------------------------------------------------------------+

.. include:: /reference/forms/types/options/_debug_form.rst.inc

Field Options
-------------

.. include:: /reference/forms/types/options/alpha3.rst.inc

.. include:: /reference/forms/types/options/choice_translation_locale.rst.inc

Overridden Options
------------------

choices
~~~~~~~

**default**: ``Symfony\Component\Intl\Intl::getLanguageBundle()->getLanguageNames()``.

The choices option defaults to all languages.
The default locale is used to translate the languages names.

.. caution::

    If you want to override the built-in choices of the language type, you
    will also have to set the ``choice_loader`` option to ``null``.

Inherited Options
-----------------

These options inherit from the :doc:`ChoiceType </reference/forms/types/choice>`:

.. include:: /reference/forms/types/options/error_bubbling.rst.inc

.. include:: /reference/forms/types/options/error_mapping.rst.inc

.. include:: /reference/forms/types/options/expanded.rst.inc

.. include:: /reference/forms/types/options/multiple.rst.inc

.. include:: /reference/forms/types/options/placeholder.rst.inc

.. include:: /reference/forms/types/options/preferred_choices.rst.inc

.. include:: /reference/forms/types/options/choice_type_trim.rst.inc

These options inherit from the :doc:`FormType </reference/forms/types/form>`:

.. include:: /reference/forms/types/options/attr.rst.inc

.. include:: /reference/forms/types/options/data.rst.inc

.. include:: /reference/forms/types/options/disabled.rst.inc

.. include:: /reference/forms/types/options/empty_data.rst.inc
    :end-before: DEFAULT_PLACEHOLDER

The actual default value of this option depends on other field options:

* If ``multiple`` is ``false`` and ``expanded`` is ``false``, then ``''``
  (empty string);
* Otherwise ``[]`` (empty array).

.. include:: /reference/forms/types/options/empty_data.rst.inc
    :start-after: DEFAULT_PLACEHOLDER

.. include:: /reference/forms/types/options/help.rst.inc

.. include:: /reference/forms/types/options/help_attr.rst.inc

.. include:: /reference/forms/types/options/help_html.rst.inc

.. include:: /reference/forms/types/options/label.rst.inc

.. include:: /reference/forms/types/options/label_attr.rst.inc

.. include:: /reference/forms/types/options/label_format.rst.inc

.. include:: /reference/forms/types/options/mapped.rst.inc

.. include:: /reference/forms/types/options/required.rst.inc

.. include:: /reference/forms/types/options/row_attr.rst.inc

.. _`International Components for Unicode`: http://site.icu-project.org
