Demo app en rails 7

bootstrap via

* gem "bootstrap"

popper y jquery por importmap:

* pin "jquery", to: "https://code.jquery.com/jquery-3.6.0.min.js", preload: true
* pin "bootstrap", to: "https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/js/bootstrap.min.js", preload: true
* pin "@popperjs/core", to: "https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.5/dist/umd/popper.min.js", preload: true


rails action_text:install .Funciona con active storage out of the box, pero no me renderiza las imagenes.

para solucionarlo, en gemfile:

* gem "mini-manick"

en application.rb:

config.active_storage.variant_processor = :mini_magick

segun: https://github.com/rails/rails/issues/44211

---

rails g mailer comments submitted

----

para comments asincronico
added broadcasts_to :post in comment model and turbo_stream_from @post for show.html.erb
