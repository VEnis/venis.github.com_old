---
layout: post
title: "Static pages in Symfony"
description: ""
category: Symfony
tags: [staticpages]
---
{% include JB/setup %}

Almost all websites have some kind of static pages that does not need any logic.
Usually they have empty controller that looks like:

    public function aboutAction()
    {
        return $this->render('AcmeBundle:Pages:about.html.twig');
    }

You also need to reference them in the routing configuration:

    about:
        pattern: /about
        defaults: _controller: 'AcmeBundle:Pages:about'

Annotations usage simplifies things but it still too much work:

    /**
     * @Route("/about", name="about")
     * @Template
     */
    public function aboutAction()
    {
        return array();
    }

Instead that you can use built-in symfony's controller **FrameworkBundle:Template:template** and configure
everything right in the routing configuration file:

    about:
        pattern: /about
        defaults:
            _controller: FrameworkBundle:Template:template
            template: 'AcmeBundle:Pages:about.html.twig'

If You look at the controllers source You will see that it simply renders passed template using **templating** service:

    // vendor/symfony/symfony/src/Symfony/Bundle/FrameworkBundle/Controller/TemplateController.php
    class TemplateController extends ContainerAware
    {
        public function templateAction($template)
        {
            return $this->container->get('templating')->renderResponse($template);
        }
    }