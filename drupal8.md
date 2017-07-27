# Drupal 8 

## Code

#### Get Current ...
* Node > `$node = \Drupal::routeMatch()->getParameter('node');`
* URL > `\Drupal::request()->getSchemeAndHttpHost()` = http://site.dev

#### Classes ...
* EntityReferenceFieldItemList
	* `->referencedEntities();`
	* `->first()->get('entity')->getTarget()->getValue()` > Gets Referenced Entities.

#### Kill Static Page Cache
`\Drupal::service('page_cache_kill_switch')->trigger();`

#### Load module code
` \Drupal::moduleHandler()->loadInclude('module_name', 'module');`

#### Drupal.org Contrib
* Patch file naming `[project_name]-[short-description]-[issue-number]-[comment-number].patch`

#### phpcbf
`../vendor/bin/phpcbf -n --standard="modules/contrib/coder/coder_sniffer/Drupal" modules/custom/custom_module_name/`

## Theme
* Theme a form

  This Requires a hook_theme().
  ```php
  return [
    'form_id' => [
      'render element' => form
    ]
  ]
  ``` 

## Other Notes to self
* When creating a custom views filter, make sure you create a schema file to map the schema settings. (e.g. `config/schema/module.views.schema.yml`)