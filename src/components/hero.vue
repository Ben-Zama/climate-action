<template>
  <section id="hero">
    <div :class="['mobile-menu', { active: mobileMenu }]">
      <a href="#future">Projected Future</a>
      <hr />
      <a href="#causes">Causes</a>
      <hr />
      <a href="#solutions">Solutions</a>
      <hr />
      <a href="#success">Success Stories</a>
      <hr />
      <a href="#action"> Take Action </a>
    </div>

    <header class="fade-in1">
      <a href="#" class="logo">
        <img src="/logo.png" alt="" />
      </a>

      <nav>
        <a href="#future">Projected Future</a>
        <a href="#causes">Causes</a>
        <a href="#solutions">Solutions</a>
        <a href="#success">Success Stories</a>
      </nav>

      <div class="ctas">
        <div class="sdg">
          <a target="_blank" href="https://globalgoals.org/goals/"
            ><img src="/sdg.png" alt=""
          /></a>
          <a
            target="_blank"
            href="https://globalgoals.org/goals/13-climate-action/"
            ><img src="/climate-action.png" alt=""
          /></a>
        </div>
        <a href="#action">
          <CTA label="Take Action" />
        </a>
      </div>

      <label class="hamburger">
        <input @click="toggleMenu" type="checkbox" />
        <svg viewBox="0 0 32 32">
          <path
            class="line line-top-bottom"
            d="M27 10 13 10C10.8 10 9 8.2 9 6 9 3.5 10.8 2 13 2 15.2 2 17 3.8 17 6L17 26C17 28.2 18.8 30 21 30 23.2 30 25 28.2 25 26 25 23.8 23.2 22 21 22L7 22"
          ></path>
          <path class="line" d="M7 16 27 16"></path>
        </svg>
      </label>
    </header>

    <div class="hero">
      <div class="fade-in1">
        <svg viewBox="0 0 1132 567" class="svg-eye">
          <path
            fill="#306F3A"
            d="M566 566c208.03 0 396.36-94.17 565-282.5C962.36 471.83 774.03 566 566 566c-208.03 0-396.36-94.17-565-282.5C169.64 471.83 357.97 566 566 566z"
          >
            <animate
              attributeName="d"
              begin="0ms"
              dur="325ms"
              fill="freeze"
              values="M566 566c208.03 0 396.36-94.17 565-282.5C962.36 471.83 774.03 566 566 566c-208.03 0-396.36-94.17-565-282.5C169.64 471.83 357.97 566 566 566z;M566 566c208.03 0 396.36-94.17 565-282.5C962.36 95.17 774.03 1 566 1 357.97 1 169.64 95.17 1 283.5 169.64 471.83 357.97 566 566 566z"
            ></animate>
          </path>
        </svg>
        <svg viewBox="0 0 480 480" class="svg-globe">
          <defs><circle id="a" cx="240" cy="240" r="240"></circle></defs>
          <g fill="none" fill-rule="evenodd">
            <mask id="b" fill="#fff"><use xlink:href="#a"></use></mask>
            <use fill="#306F3A" xlink:href="#a"></use>
            <circle
              cx="240"
              cy="240"
              r="233"
              stroke="#3F7E44"
              stroke-width="14"
            ></circle>
            <g fill="#3F7E44" fill-rule="nonzero" mask="url(#b)">
              <path
                d="M395.4 355.8c.2 1.4-.3 4.6.3 5.3.6 1 3 1 4 .5 2.8-1 5.6-4.7 7-7.5.8-1.4 1.4-3 1.2-4.8l-2-6c-.5-2-1.2-5.7-3.4-6.5.2-.6 1-1.5.8-2.2-.5-2.4-4.4-1.8-5.8 0-.7.8-.5 2.6-.7 3.7 0 2-.7 6.4-1.5 8.4-1 2-3.3 4.5-3.3 6.6.2 1.6 2 2.5 3.2 2.6zm-130-16.4l.7 1.6c0 .2.4.7.7.7 1.8 1.7 4.2-2.2 1.3-2.8-.3 0-.8-.3-1 0-.6 0-1 0-1.6.4zm-29.6-27c-2 1.8-1.8.7-2.8 1.3-.7.6 0 1.4-.8 2.5-.2.5-1 1-1 1.4 0 .8.8 1.3 1.6 1.4 1 .2 4.2 0 5.2-.7 1-1 .6-2 1-2.7.3-.3.7-1 1-1.2 0-1.3-2.7-3-4.2-2zm75.8-8l.3 2.5-.4 2c2.8-.5 4.6-1.4 7-2.4 1-.4 2.4-1 3-.6.8.5.4 1.3.2 2-.5 1-2 3-2.8 3.8-2 2.3-5.3 2.6-8 5-1.3 1.4-1.7 2.8-3.2 4.3-1.4 1.5-2.4 2-3 2.5-.8.8-.3 1.3-1.7 2.2l1-2c-1 0-2 0-2.6-.8-.3-.8-.4-1.6-.2-2.4.3-1.6.7-6 1.6-7 .2-.3 2.3-1 3-1.4l-.3 1.6c.8 0 2 0 2.6-.5 1.4-.3 2.6-3 3.3-4.2l-3.5 1.5c.6-1.7 2.3-5 3.8-6.2zm-70.3 7.8c-.5 2.4 1 1.5 2 2.5.4.4.5 1.2.6 2l-2.2.5-1 1.4-1 1.4 3.5 1c-1.8.7-2.8.5-4 2.2l4.5-.4c3 0 5 .6 7.8-1l-.6-.4.8-2.5-2-1.2-.7-1.5-3.2-4-1-.4c1-1.3 2.7-3.3 0-3.8l-1.3-.2 1.2-1.4c-1.6 0-3-.3-4.2 1-1.4 1.6-1.4 3.7.8 4.6zm-1.5-34v1.8l-.7-.7.2 3c.4 2 2.5 1.3 3 .7.4-.3.6-1.4.5-2 0-.5-.3-1-.6-1.2-.5-.2-.8-.2-1.3 0V278l-1 .2zM24 295c-.2 4 1 3.8 1.8 7 .4 2-.3 2.5 1.2 6 .7 1.6 1 3.2 2.7 3.8-.4-4.4-1-7-2.5-11-1-2.7-2-3-2.7-6H24zm361.7-43.7c-1.2.6-1.6 1.5-1.5 2.8 0 1.4 1 2.4 2.3 2 1.8-.7 2-5.2-.8-4.7zm-170.2.7l1 .7c1.8-1.8 2.2-3 3.6-4.6 1.3-1.3 2-1.4 2.8-2 .5-.5.4-1 .6-2 .4-1 1.2-1.3 1-3 0-1.7-1-4-2.8-3.6l-.4-1.3c-.8.2-2 .6-2.8 1.2-.7.6-.3 1.6-1.3 2.5-1 1.4-3 2-3.6 2.4-.7.5-.4 1.2-1.6 2-1.7 1.3-3 .6-4 1-1.2.4-3 2.4-4 3.3-1.4 1.7-1.8 2.8-2.4 4.7-.2.5-.7 1.4-.4 2 .4.4 1 .3 1.6 0 1-.4 3.3-1.6 4-1.4 1 0 1.2.4 1.8.6l2 .4c.4.2 1 1 1.6 1.4 1.4.7 2.8-1 3.2-2 .2-.7.4-1.2.3-2zm4-18.4c.6 1.6 3 3.2 4.6 4.4.6-.3.8-.6 1-1.2.7-1.3.4-4-1-4.6-1-.5-2 0-2.6.2 0-.3-.4-1-.7-1.3-2-1.8-4.6 3.7-1.3 2.6zm-11-3.5c1.7 1.8 1.7 2 4 2-.3 1.5-2.4 4-4 3-1.2-.8-1.3-2-2-2-.7-.5-.8 1.3-1.3 2-1 2-3 1.8-3 5l1-.7c1 2 2.7-.2 4-1l-1 1.5c0 1 .8 1.6 1.5 1.2.8-.3 1.7-1.7 2.4-2.3l2-1 2.3-2c2.2-1.8 2.3-.8 3-3.5 0-.5.3-.8.2-1.3-1-2.4-4.8-.5-5-.7l-1.7-.4c-.6-.3-1.6 0-2.4 0zm12-.4h-1.3l.4.8c1.5-.4 2.6-.5 2.6-2.3-1.3.2-1.6.2-1.7 1.6zm-82.5 5l-1.2 6 .6 2.5 1 5.3c.7-1 2-4.7 2-6l.4-2c0-1.7.3-2.3-.4-3.8l-1.7 1.5v-3.5h-.7zm85.2-7c0-1.4.2-1.2 1.5-1v-2.7c-.8.2-1.8.3-2.6 1-1 1.3-1 2.7 1.2 2.7zm-7.7-3.4l1 1c1.7-.5 2.2 0 4 .4l-.8-1 .7-1c1.6-.3 1.7-1.6 1-3-.3 0-.8-.3-1-.6-3-1.6-3.2 1-4 2l-1 2.2zm6.7-1c.6 0 1 0 1.6-.3 1-1 .4-3.6-.4-4-1-.2-1.3.6-1.2 1l-.2 1v1.3l.2 1zm-75-10.4c.4 2.4 0 4.5-.7 6.7-1 2.5-3.6 6-4.2 8.3l-.6-.7c-1 1.8-1.2 5.5-.5 7.3 1.4-1.5 1.7-3.3 2.6-5 1.7-3.6 4-6.7 5-10.8 0-1 .3-4-.3-5-.4-.5-.6-.5-1.2-.7zm238.6 7c1.4-2 1.7-6 2.3-8.5 1.3-5.6 4-8.2 3.2-15.3-.2-1.6-.8-4.7-2.7-5-3-.4-1.7 3.5-2 4.3.2.8 0 1.4-.2 2-1.3 2.7-.7 5.8-.7 8.7l-.5 9.6.8 4.2zm-42.4-45.2c0 .5.3.7.6 1.2l1 .8c1.6 1 2.5-.8 1.8-1.8-.3-.5-1.3-.7-2-.6-.4 0-1 0-1.4.4zm39.2-4.6c.2 2.4 1.2 6.2 2.2 8.3l2.3 4.3 2.8 8.2c1.4-1.7.7-3.8.2-5.6-1.2-3.6-3-7-4.3-10.5-1-1.7-1.7-3.5-3-4.7zm-14.5-4.3v3l-3.7-1.3c0 2 .8 4.7 2.2 6l3 2.3c2.2 2 4.6 4 6.7 6.3 1.8 2.2 2 3 2.5 4 .6.4 1.2 1 2 .6.4-.3.6-1.7.8-2.2l.8-1.7c.4-1.3-.6-3.4-1.3-4.6l-1.7-3.7c-.7-1.8-1-3.4-2.4-5-2-1.8-3.7-1.7-6-2.3l-3-1.3zm-72.8 3.7c0 1-.2 2.6-1.5 3-.3 0-1.3 0-1.6-.4l-1 3c-.4 1-1.2 3-1 3.8-.2 1.4 1.6 1.2 2.5 0 1-.8 1-2.2 1.8-3.3 1-2.2 3-3.2 3.3-5.8l-2.4-.3zm81.2-10c.8 2.3 1.3 2.6 2.6 4.6.7 1.2.5 2 2 1.6-1-1.2-3.5-5.5-4.6-6.2zm-109.8 14c-3-.2-1 3-1.4 4.5-.6 1.3-3.6 3.4-5 2.4-.8.4-1.6.4-2.4.3-.8-.2-1.4-.7-2-.6l-4.3 3c-.7.7-1.7 1.3-2.8 1.4-.8 0-1.8 0-2.3.7-.7.7 0 2.2.3 3l1.3 1.8c-2.6.7-2.4 2.5-2 5 0 1.2.5 6 1 7 .3 1.3 2 2.4 3.4 2.8.8.5 2 .6 3 .6V202h1l.7 2.5h1.2l3.2.6.6.6c.3.8-.3 2.2-.2 3 .4 1.8 2.3 2 4 2v3c0 1.2-.7 1.3 1 4 .2.5 1 1.8 1.7 1.7.8 0 2.4-2 4.2-3 .4 1.3.4 1.6 1.5 2.3l-.4 1.3 3-2c-1 4-2.6 3.2-4.4 5.8-.6 1.3-.2 2.6-.6 4l.3.2 1-.6.8-.3c2.3-.4.5 2.4.6 3 0 .7.6 1 1.2 1.2l-1.2 1 .7 1.7-4.6.3c-2.4.4-4.3 2.2-6.2 3.7v.5l.8.2-4.5 2.3c1.4.4 3-.3 4.5-.4 1.2-.4 1 0 2.6-.5l.8.5-.2 1 5.8 2c1.4.4 2.4-.2 3.2.2 1 .7.7 2 2.6 2.4 2.2.7 4-.5 5.7-1l-2 2.4 1 1.8 2.5-.8c-2 2-2 .4-5.5.8l4 1.7c1.2.3 2-.3 4 .4 1.5.4 3.5 1.5 4-1 .3.6.7 1 1 1.3.8.5 1.3.4 2 .6 1.2.2 3.8 1.8 3.6 3 0 .4-.3.7-.6 1-.3-.8-.7-1.5-1.3-2.3-1.4-1.7-3.7-1-5.6-1.3l-3.8-1-3-.3c-1.5 0-2.4-1-4-1-.5 0-1.3.5-1.2 1 0 .5.6 1 1 1.2 1.6 1 1 .2 3.6 1.8 1.4 1 2 .6 3.2 1l1.4.7c1 .3 1.3-.3 2.4 0 .5 0 1.6 0 2 .2l-4.4 2-3.5-.4c.8 1.5 1 1.7 0 3.2l-.7-1c-.7.8-.7 1.3-1.4 2.2l-1.2 1.4c-.2.6-1 1.4-1.5 1.5-.7 0-1.6-.8-2.2-1.3-1-.7-1.6-.7-3-.3 1 1.5 1.6 1.2 3 2 1 .6 4 3 5 4-.3 0-.6 0-.8.5-.5.5 0 2.8.6 3.6.6.5 1.2.7 2 .6l-3.2 3c1.4.3 2 0 3 1l-2.6.2-3.4-2.6-3.6-1.5c1.3 0 3.5.2 4.7-.4 2.2-1.4 1.2-4-.6-5.4-1-.7-1.8-.6-3-.7-1.2-.3-2.8-1-4-1l-2.8.7.2-1c-.8 0-1-.3-1.8.3-1-.7-1-1-2-1l.2 1.2-1.2-1.2v1.3c-.8-1-.8-1.3-2-1.7l1 3.4-.5.8c-1.3 1.2-1.3 3.8-1 5.4.2 3.2-.5 4-.8 6.4 0 2 .6 2.6 0 5.3 0 1-1 4-1.5 4.8l-1.2 1.5-1 1.6c-.3.8-1 1.3-1.5 2.2-.4 1 .2 1.6.5 2 .5 1.6-.6 1.2 1.2 3.4l-1 1h1c-.5 2 .7 3.2 2.5 2.7 1.3-.3 2.7-2 3-3.4l.6-.2 3.5 5.8c.6.8.8 2 1.8 2.2 1.2.2 1.6-1 2-1.7l1.5-1.4c.6-1.4-.6-3.4-.5-4.7 0-1.2 1-1.8 1-3-.2-2-1.6-2.3-2.5-3.3-1-1-1-2-1-3.4-.4-2.8 1-3.8 1.3-6.2 0-1.5-.8-2.5-1-3.5 0-.8.2-1.6 1-1.7 1.8-.4 2 1.7 2 3v2.7c-.2 1-.7 2-.5 3.2.3 1 1 1.8 1.3 2.5.6.8.7 1.6 1.3 2 .4.2.7.5 1.2.4.6.3 1 .5 1.7.4 1-.4 2.5-3 3.7-3.8.7-.6 1.8-.4 2.6-.5-.5 1-1.6 2.3-2 3-1 .5-3 1-3 2.5-.6 2.2 2.3 2 2.3 3.8-.2 1.3-2.2-.4-2.8 1.3-1 1.7.3 2.6.7 4 0 .7-.4 1.5-.6 2.3-1.2 2-2 .7-3.6 1.7-1.2.6-2.6 2.6-4 3-1 .3-1.8-.4-2.6-.3-1 0-2 1.7-3.6.3-1.8-1.7.2-2.7-.2-4.2l-1-2.5c-1.6 1-3 2.2-2.5 4.2.7 1.8 2.4 3.3 1.5 4.7-.7.6-2.3.7-3.5 1.6-1.5 1-3 3.7-3.5 4-.8.6-1.6.7-2.3 1.3L250 325c0 .2 0 .2-.4.5l-3.3-1 .2 1.8H244c-.7-.3-2.3-.4-2.7.7-.4 1 1.8 1.5 2.3 1.7 3.4 1.5 4 5.2 2.6 6.6-1 1-2.6.3-3.7 0-2.4-.2-6.2-1.2-8.6-1.3-3.3.3-2.3 2.4-3 4 0 1-1 1.7-1.2 2.5-.2.3-.2.5-.2.8 0-.3 1 3 1 2.8.2 1.2 2 1 3.2 1.2 1.3.4 1.7 1.2 2.8 1.8 1 .5 1.6.2 2.6-.2 2.4-.2 4.6 1 8-1 1-.3 1.6-1 1.8-1.5.7-.8.4-1.6 1.3-2.5 1.2-1 3.5-1.6 4.8-2.5 1-1 .3-2.4 2-3 1.4-.5 2.8.4 4.6-.2 1.5-.3 3.2-2 4.7-2.5 1.6 0 2.6 1.6 4.8 2.2l8.7 2c.3 0 1 0 1 .3 2.5 2-1 2.8-2.2 3.2-1 .3-1.2.3-2.3.4l.6.8c1 .4 3.8.7 4.8-.2.4-.6.4-1 .3-2 1-.2 1.4-.5 1.8-1.6 0-.8-.4-1.6.3-2.2.6-.5 1.6-.6 2.4-.7-1.2-1.5-2.2-1-3.8-1-.8-.2-1-.7-2-1-.7.2-1.5.8-2.6.4-.8 0-1.6-1-2.5-1-.8-.5-3-.8-2.8-2.2.2-.5.4-.8 1-1l.7-.2.4 1c2.8-1 1.8.4 4.3.7 2.2.6 4.8 0 7 .7 1.4.4 1 1.3 2 2.5 1.6 1.2 3.7.7 5.5.6-.2.3-.5.4-.5.6-.4 1 .2 1.3.7 1.5 2 1.3 5-1 2.4-2.2l4-2c-1.8-.8-2.8 0-5.3-1.6 1.3 0 1.5 0 2.5-1v-1l4.4-2.3c-1.4 2 .2 1.5.7 3.8 1.3 0 3 .3 4.2.2 1-.4 3.8-1.4 4.6-2 .8-.6 1-1.4 1.7-2l3-1.4c1.3-1 2.2-2 3-3.2.6-.5 1-1 2-1 1 .5 1.3 3.2 1.4 4.2.4.8.8 1.8 1 2.6-.3 3.4-4 4-6 5.8-1.6 1.2-2.7 3.2-4.2 3.8-2 1.5-7.5 3.6-10 4.4l-5.5 1c-1.3.6-2.7 1.8-3.2 3-.3 1 .4 2.3-1 3-1 .6-6.3 1.3-7.7 1.2-2-.4-1.4-1-4.5-.7-3 .3-6 .8-9 .3.5-.6 1.4-1.7 1.6-2.6.2-.5 0-.7 0-1.3-.2 0-.2-.6-.5-1-.7-.6-2.8-.4-3.6-.4-1.8.5-1.5 1-4.4 1.2l-9.6 1c-4.7.6-8.5 2.5-10.3 2.7-1.3 0-4.2-.2-5.6-.6-1-.5-2.2-1.5-3.5-.8-1.4.3-1.8 1.4-3.3 2-1.5.8-4.4 1-6 2.2-1.8 1.3-1 2.2-3 3.2-1 .4-4.4.4-5.7.5-3 0-4.4 1.3-7 2.3l-2.7 1c-1 .4-3 1-3.5 1.7-.5 1 .2 2 .3 2.6.2.8 0 1.6-.2 2.5-1.4 2-5 3.7-4.3 6.5.4 1.8 1.5 2 3.5 3.7 2.7 2.7 4.7 6.5 7.6 8.6 3.7 2.6 9 5.8 13.7 6.7l8 .3c4.2.5 7.5 1.5 12 1.3l9.8-1.5c2.2-.2 5.3-.8 7.5-.2 2.2.6 2.6 2.2 6.6 1.8l5.5-.6c1.3-.4 2.3-.8 3.7 0 3.4 1.7-2.3 5.2.3 7.3 1.4 1.2 6.2 1.6 8.2 2.2 1.3 0 5.5 2.3 6.4 3.3.7.5.7 1 1.4 1.7.6.8 2 1.2 2 2 0 .7-1.6 2.2-2 2.8-1.5 1.4-4.3 5-2.7 7.4.6.7 2.3 1.4 3 1.8l7.7 2.2c3.3 1.3 3.6 4 5.6 5.4 1.5 1 3.8.7 5.7.8l8 2c2.6.7 1.4 2.4 3.6 2.8 4.5.4 11.5-3.7 15.2-6.2l7.5-3.8c3-1.6 5.7-3.4 8.4-5.3 5.2-4 9.4-9 12-15 .8-1.6 3.3-5.5 3.5-6.6.2-1.6-1.5-2.5-.8-4 .8-1.8 4.2-4.5 5-6.7.7-1 .5-3-.6-3.7-1-.4-1.8.2-4-.4 1.6-4.4 4.6-8.6 7-12.5 1.2-1.6 3.3-4.7 3.3-7 0-2.2-2.2-2.3-3-3.3-1-.7-.8-1.3-1.3-1.5-1-.4-3 .5-4 .4-.7 0-1.3-.4-2-.6-.7-.5-1.7 0-2.5 0-1.2-3.7 1.3-10.3 2.5-13.8 2.3-7.6 5.5-15.3 4.3-23.4l-1.2-6.3c-.3-.8-1-1.8-2-1.4-1.5.5-3 5-3.5 6.5l-3.6 6.4c-1 1.3-1.4 3.2-2.6 4.4-1 1-2.4 1.5-3.7 2.2-.4-1.3-1-1-2.2-.6l-4.6 2.5c-1 .7-3 2.2-4.3 2.3-1 0-1.5-.7-3-.3-1 0-3 .8-3.7.6-1 0-2.2-1-3.3-1.2-.8-.2-2.4.2-3 .6-2.7.2-6.8-1-9.5-1.6.4-.3 1-.3 1-.8.3-1.4-1.8-3.6.8-4.4h1l4.5-.2 2.6-.5c1.3 0 1.7.8 3.5.7l6.3-1.7c2.7-.2 3.7 2.3 6.4.5 2.3-1.5 4.3-6.7 5-9.2l2.4-5.8 1-4c1-3 2-4.4 1.6-7.8l-.6-5c-.2-2-.6-3.7-2.8-1.6-1.7 1.8-2.3 3.7-5 3.4-.6 3.3-.2 7.5-3.4 9.4-1.3 1-2.6.4-4 .8-.7.4-1.6 1-2.2.8-.8 0-1.4-.4-1.4-1.2 0-1 2-1.8 2.6-2 2.6-1 4-1.5 5.7-3.8 1.2-1.7 1.3-3 2.2-4.4 1-1.2 1.7-1 2.7-2 .7-1 2-3.8 2.6-5l3.2-9.4c1.6-2.8 4.2-3.3 5-6.8l.3 1.3c2.7-1.2 2.7-4 2.2-6.5 1.5 0 4.7 0 6-.3l6-3.7c1.5-1 4-2.7 4.3-4.3.4-1-1.3-4.7-2-5.4-.3-.5-.5-.8-1-1-1.5-.4-3.3 0-4.3-1.7-1.2-1.4-2.5-6.6-3.5-8.6-2.2-5.4-2.3-4.3-3.4-6.3-.6-1.2-.5-2.5-.7-4-.2-1-.8-1.6-1-2 0-1.2.7-1.8 1.4-2.6 1-2 1-3.6 2.2-4.7 1-1 1.8-.5 2.2-1.3 1.6-2.3-2.3-4-1-6.5.7-1.3 2.6-3.3 4-3.4 1-.4 1.8 0 2.8-.3 1-.6 1-2.4 1.5-3.5 1-2.8 2.7-2.7 3-6.4.2-1.3.3-3.2-.4-4.2-1.2-1.5-3-.3-3.3.8-1 1.4-.7 3.3-.6 5 0 1.5-.3 3.6-1.2 5-1.2 2-3.4.6-4-.4-.4-.5-.2-1-.2-1.6 0-2-.6-3 0-5.3 0-1 1-4 .8-4.6 0-.7-2.4-3.4-3-4-1.2-1.3-3.4-4-5.4-2.8-1.7 1-1.3 4.4-1.7 6.2-.2 1-.6 2.5-1.4 2.5-.5.3-1.3-.5-2-1-1.4-1.4-2.3-2.4-2.6-4.7 1 .2 3 .8 3.2-.3 0-1-1.4-2.8-2.4-2.7-1-.2-1.2 1-2.7 0-1-1-3.6-5.3-4.8-6.8-1.6-2-3.8-3.6-6-4.7-1.4-.4-6-2-7-1.2-.6.3-.5 1-.7 1.6-.3-.2-.6-.5-1-.4-2-.4-2.6 1.8-2.7 3 0 .7.2 1.7-.6 2-.7.4-1.3 0-2-.6-1.3-1-1.3-1.2-3.3-1.8.3 1 .7 2 1.3 3 1.6 2 2.6 2 2.4 4.6-2.2-1-4.7-2-6.2-3.7l2-.7v-.5c-1-.4-3.8-2.5-4-3.5 0-.8 1-1 1-1.7.2-.8-.7-1.3-.3-2.4.7-.8 2.3-1.5 2-2.5 0-.7-.5-1-1-1.4-1.2-.7-3.2-2-4.4-1-1 1-.2 2.8-.8 5.2-.8-.2-2.2-1-3-1-1-.2-2.3.4-3.7-.2-2-.7-2.6-2.2-4.3-2.8-3-1.4-5.6-.6-8.4 0-1.3 0-3.4.2-4.7 1-1 .5-1.5 1.3-2 2.2-1 1.4-3.4 2-3.2 4.2.5 1.8 2 2 2.6 2.4l1.7 3.3c-1.7.4-2.5 0-4 0l-6.3 1.4c-3.2 0-4.2-1.8-6-2.6-1.2-.5-2-.4-2.8-1-1-.6-1-1.4-1.4-1.6-.6-.7-3.3-1-4-1 0 .6 0 .8-.4 1.4-.5.8-2.7 2-3.8 2.2-.5.3-1.3 0-1.8 0v-1.2c.2-1.3-.5-1.2-1.6-1-1.5.5-2.4 1.7-3.7 2.6.5-1 1-2 1.6-2.8 1-1 2-1.3 3.4-2l4-2.4c1-.6 2.5-1.3 3.2-2 2.2-1.7 2.6-7.3 2-10-4 1.6-3 1.7-5.7 3.3-1 .6-1.6.7-2.3 1-.8.6-1 1.4-1 2.2zm27.8-9.5l2.6 1.8 2 3.5c1.4-.7 1.6-1.2 2.7-1.6.5-.3 3.7.5 3-1.6-.3 0-.6-.4-1-.6v.8c-1-.7-2-1.7-3.2-2-1-.5-4.8-.4-6-.3zm8.8 1.2c3.7-.3 3-1.3 5.2-1.5 1-.4 2.6 0 3.7.2v1c2 .8 2-.5 3.6 0 1.7.5 2.7 2.5 5.4 3.4 1 .4 1.7.6 2.7 0 .6 1 1 1 2 1 0-1.5.8-1.8.5-2.6-.4-.7-3.2-1.8-3.4 1-1-1.4-.4-1.7-.8-2.4-1-1.3-2.8-1.4-4-1-.6-2.6-.2-1.8-4-3.6-1-.7-3.5-1.8-4.8-2-1.6 0-2 1-3.3 1.7-.8.8-1.6.6-2.3 1.2-.7 1-.6 2.4-.5 3.5zm55.4-11.6l3.3 3.7c1 1.7 2.4 3.5 4 5 1 1 2.7 1.5 4.2 1 1-.2 4-3.4 1.6-4.8-.8-.4-2 .2-3 .3.2-2 0-3-.4-4.8 0-.5-.2-1.5-1.2-1.2-1.2.7.2 4.5-1.7 3.4l-1-.5-.7-.7c-1 1 0 1.6 1 2.5 1.2 1 2 2 2.3 3.6-2.8-1.8-3-3.4-4.8-5.6-1.2-1.2-2-2-3.6-1.8zM370 151c.7 1.8 3.5 5.8 5.4 6.4-1.3-2.3-3-5.6-5.5-6.4zm-191.6 19l7 2c1.7.4 3.6.5 5 2.3-3.6.3-2.8-.3-5.5-1-2.5-.2-3.3.4-5 .3l-2.6-.6-7 1.2c-1.8 0-2.3-1.4-3.4-1.8-1-.7-2-.4-3 .3-2 .7-3.6 2-5.3 3-3.2 2.2-7 4.7-9.2 7.8-1.6 2.3-1.2 3.5-2.8 5.8-1.7 2-5.4 4-8 7.3-1.8 2.6-1.7 4.2-2.4 5-.4.6-3.7 2.5-4.4 2.8-1 .3-1.7.4-2.2.7-.7.7-1 1.5-1.6 2.4l-2.6 3c-.6 1-3.4 5.2-3.5 6.3 0 1.8 3 2.6 1.4 5l-.7 1c-1.7 1.2-2-.6-3.5-.7-1.6-.4-4 1.6-5.5.5-1-1-.5-2.4-.6-3.4-.3-1.2-1-1.7-1.3-2.7-.6-1.3 0-3.7-2-6.2-1-1.4-2-1.8-3 0l-.5 1.7c-1-2.3-.4-4.2-2.3-4.5-2.5-.3-3.3 2.6-4.7 4.4-3.5 4.2-4 3.8-6.7 6L89 221l-2.2 1.6c-1.2 1-2 3.6-2.6 5.2l-2.6 10.6c-.5 2-1.5 5.7-3.8 6.4-.7.3-3 .3-4 0-.8-.4-1.4-1-2.2-1.3-.8 0-3 .3-4.8-.6-1.2-1-2.7-2.8-3.8-3.3-1-.4-2.2-.3-3.2-.2-1.3 0-3.2.3-4.2 0-2.8-.7-4.5-4.8-5.6-7-.4-1-1-2.6-2-3-1-1-2.5.7-3.8.3-1-.2-3.5-2.6-5-3.3-.2-.3-1-1-1.5-.7-.5 0-.7 1.2-1 1.7 0 2 .6 2.6 2 4 0 .3 1 1.3.3 2-1.2.8-3-3.3-4.3-1.3-.2.5-.2.8-.5 1l-1.7-4.2-.2-2-1.8-4-2.2 2-.5-2.3-.7-1.7c-.3-1.3-1.3-1.2-2.3-.6-2 1.5-3.3 3.7-4.6 4.6-1.3 1-2.5.3-3.5.6-1.3.7-2 2.3-2.5 3.7L12 240c-1.8 8.4-3 10.4-2 19.3l1 5 1 6.7 1 3.4c.2-3.5.3-9.8 1.3-13 1-3.6 2.4-4.3 2.5-8.5l.6 3.3c1.4-1.5 1.3-2.5 3.3-3.5.7 1.2 1 1.5 1.4 3 .5 1.3.6 2.4 1.3 3.6.7 1.3 1.2 1.5 2 2.5.5.7 1 2 1.2 3 .8 1.8 1.3 4.6 3.5 5.2 1-2 .6-4.3.7-6.4.2-.5.3-2 .7-2.4 1.3-.4 1.8 2 2 2.7.7 2.2 1.2 4.8 2.5 6.5 1.2 2.3 2.2 2 4 5.5l.3-1.4c.7 1.8-.2 3.2 1.8 4.3 0-1-.3-5.6.2-6.4.2-.6 1-.6 1.5-.7l1.2 8.8c0 1 .4 2.3 1 3 1.5 1.5 3.2.3 4 1.6l1 4.7c.8 3.4 2 7.6 3.4 10.6 1 2.3 2.5 5.4 4.2 7 .7.8 1.5 1.8 2.6 1.4 1-.3.6-1.6.8-2.4 0-1 .6-1.4.8-2.2 0-1.4-.3-3 .3-4-.2 1.6.3 1.8.5 3.4.2 2 .8 4.4 1.5 6.5 1 3 2 6 3.8 8.6 1.3 1.7 4.2 3.8 6 5.2 2.3 2.5 4.6 4.6 7.5 6.8l3.4 2.3 3 2c2.4 1.2 2.7-1.2 4.2-1.3.8.2 3.6 2.3 4.5 3 4.4 4 3 3 6 6.6l7 7.4c1.6 1.6 3.8 5 6.2 5.2l2.5.3c2.7.6 5.7 1.6 8.5.8 1 0 1.8-.6 2.3-1.2.7-.8 1-2 2-2 1.2.2 3.7 1.3 4.8 1.7 2.8 1.4 6.7 3.7 9.7 4.2 3 .4 5-2 4.6-4-.6-2-3.8-4-5.5-7.4-1.6-2.8-2.7-6-4.6-8.3l-4.3-5.2-2.6-4-1-1.7c-.4-.5-1-2.3-1-3l-3-7.5c-1.2-2.5-3.8-2.3-5.5-5.8 1.2 1.4 3.5 3.4 5.2 4-.8-2-2.5-5.3-3.7-7l-2.7-2.8c1.5 1.2 2.6 2.2 4.5 2.5l.6-2c.8-2.3 1.6-2.7 1.5-5.3-.3-4.5-4.4-11-5-16.5-.3-2.5.3-5 .5-7.3v-4.2c0-.8.5-1.4.6-2.5v-3c.5-1.5.7-2 .5-3.6l-1.3-4.4v-3.2l-.5-4.2c-.3-3 1.3-4.6 1.6-6.8.2-1-1.2-3.8-1.7-4.3-1-.5-2.7 0-2-1.4.6-1.3 3 1 3.6 2 .7-2.8.2-3.3-.3-5.7l-1-6.7c-.6-2-1.8-2.8-1.8-3.6 0-.8 1-1 1.8-2 1-1.2 1.4-2.5 1.5-4v-4.4c.3-2 2-5 4.4-5.7 2.3-.5 4.6 2 6 1.8 1.3 0 2-1.5 2.4-2.4l3-8.7c1.8 2.2 3.2 2.6 5 4.3l1.4 1.7c.3.3.8 0 1.3-.3 1-1.2 2.2-5.5 1.5-6.8-.4-1-1.5-2-2-3.3 0-.7.4-1.6 1-2.4.5-1.8.8-3.6 2-4.8 2.4-2.6 7-3 10-1 1.4 1.3 1.2 2 1.8 2.8 1 1 2.3 1 2.7 2.5 0 .5 0 1.8-.3 2.6.2 1.7.5 2.2 0 3.8-1 1.7-2.4 3-3 4.8-.8 2.2.5 2.4.2 4.2-.7 2-2 3.4-2.7 5.3-.7 1.2-.6 2.3-1.8 3.2-1 .6-2.6.5-3.7.6-1.5.4-2.7 1.3-4 2 0 .4 0 1 .5 1.5.4 1.5 1.7 1.4 3 1 2-.4 4.8-2 6.8-.3s2.4 6.7 4 8.4c1.4 1.2 2.4 1 4 1.5 1.2.3 2 .7 3 1.5 2 1.6 1.3 3 2.2 4.2 1 .8 1.6.4 2.5 1.4l4 6.4 2.5-2.4c1 1 2 1 2-.4 0-.8-.4-2.4-.8-3 1.8 1.6 2 3 2 5.3 0 .4-.2 1 0 1.4.2 1 1.5 3 2.3 3.8 1.2.7 2 .4 3-.2.8-1.4 1.4-4 2.8-5.6 1-1.4 3.5-2 5.6-4.5-.5-.3-2-1-2-1.7.4-1 2-1.3 3-2 1.5-1 2.6-3 3-5l-3.3-.2-2-.2-2.5.2-2.6-2H190c.5-1.5 1-2.3 2.6-2.4.7 0 1.8.3 2.3 0 1-.3.8-1.4 1.6-2 1.4-1.7 3.4-2 3.7-4.3 2.2.3 2.7-.2 3.7 0 2.2.8 3 4.7 4 6.7-2.8-.8-2.3 1.6-2.3 3.4 1-.6 2-2 3-2.4h3.6c.8 0 1-.4 1.7-.7 1.8-.4 3 .8 4 2.3 1-.6 1-1.2.3-2.2h1.3l-.7-2c-1.5 0-1.8-.3-2 1-1.3-.6-1.3-.6-2.6-.7l1-1c-2.3-1.6.2-2.3.6-3.7.2-.8 0-1.3-.4-1.8l3.2-1.4c1.4-1.7 2.6-.4 3.2-2.4 2.7.6 1.8-2.8 4-3.5.4-.4 1.2-.2 1.7-.2l2.3-1c1 0 1.6-.2 2.6-.5 1-.7 2-2 2.6-3 .4-.5 1.4-1.4 1.6-2 .2-.7-.2-1.5-.3-2.8 1 .2 2 0 2.6-.8.8-.6.7-1.6-.4-2h-1.3l3.6-3.2.6-3.2-1 .4.3-1.7-3 .3c.5-.6 2-2.3 2.4-3 1.2-.8 2.5-.6 3.2-2.3-2.6.5-5.8 3-7.4 5l-2.6 3.3.2-1c-2.6.7-2.4 2.3-3.4 3 .3.2-5 .4-4.2.6-1.3-.3-2.8-1.5-4-2.4-.8-.8-1.4-1.5-2.4-1l-5-3.7c.6-.6.8-1 .2-1.4-.6-.5-2-1-3-1.6-2-1.7-2-3.3-2.3-5.6-.2-2-.4-2-1.2-4-.3-.6-.4-1.2-1-2-.6-.7-2-1.6-3-2.3-1-1-2.5-2-3.8-2.2-2-.4-3.4.8-5 .5-1.4-.5-3-2.2-4.8-2.8-1.2-.2-2.5 0-3.5 0 0-.5-.2-1.5-.7-1.7-1-.5-2.4.2-3.5.3-1 .2-1.3-.6-2.2-.8-.7-.2-4.4 0-4.8.4-.5.4-.2 1 0 1.6.7 0 1.7 0 2.2-.2zm184.8-27c2.2 2.6 6 6.2 9.2 6.7-1-1.5-1.7-1.7-3-2.6-1.6-1-4.5-3.5-6.2-4zm-21-10.7l-.6-1.3c1 .5 2.2 1 3 2 .2.7.3 1.2.3 2 0 1.5 3 5 4.5 5 .5.3.5 0 1 0l-1.3-5c-.7-1-1.4-.6-2.3-1.5l-5.6-6.4c-.3-.4-1.5-2-1.3-2.7.6-.6 2-.7 2.4-.8l-5-4.5c-.6-.5-1.5-1.5-2.5-1-1 .2-1.5 1.6-2 2.4-.4.8-1 1.7-1 2.5.4 1 1.6 2 2.2 3l4.6 3.7c1.2 1.2 1.8 2 3.5 2.6zm68-.5c-.7-4-3.2-7.7-6.2-10.6l-4.6-3.8c-1.8-2-3.8-5.3-6.4-7.7-3-2.4-5-3-7.7-4.8l-4.4-4-8-6.4c-2-1.7-4.3-4.4-6-6.4-1.4-2.2-1-3-2-4-.5-.8-2.7-1.6-3.8-1.8l.4-1-2-1c1.2-2.2-.3-1.5-2-3.5-.5-1-.6-2-1.5-3.4-1.5-1.7-3.5-3.2-5.4-4.3L341 64c-3-1.5-7.3-3.8-10.7-4-2.7 0-4.4 1.4-7 2-2.3.4-7.3.3-9 2.6-1.6 2 2.5 5.6 4 7l4 4.2c1.3 1.2 1.7 2 3 3.5 1 1 3.3 2.3 4.2 3.5 1 1.3-.6 1.7.7 3.4 1 1.5 3.3 3.4 4 5 .3 1 .5 2.6 1.4 3.3.8.4 1.8-.2 2.6-.2 1.3-.4 5-2.4 6.2-1.7 1 .7 5 4.6 5.8 5.6.6.5 1.8 1.7 1.6 2.5.2 1.3-4-.2-3 1.6.4.5 3 2 3.7 2.6l3.3 2.8 3.7 2.8c1 .7 1.8 2.2 2.7 2.7 1.6.6 2.5-1.3 4-.4 2.7 1.3 4.7 5 7.6 7.5 2 1 2.5.8 4 1.4 1.5.6 2.4 1.6 3.8 2.5 2.3 1 2.4.3 5 2.5 3.5 2.8 6.5 5.8 9.5 9 1.3 1.2 4.2 3.8 5.6 4.2h.7l3-1.6s.3 0 .3-.3c.2-.8 0-2 .2-2.7.2-.8.7-1 .8-2.2.2-.8 0-2.4.8-2.7.8-.3 2.2.8 2.8 1zm-64-68.2c0-1-.4-1.3-.7-2.3-1.6-2.3-3.3-3.7-5.8-4.5-.8-.2-3.3-.8-3.7 0-.7 1.2 2.2 3 3 3.5 1 .7 2 1 3 1.8 1.6 1 2.4 1.2 4.3 1.6zm-102.5-22c3.4.2 4.7 0 8 1.3 3 1 4.8 2.7 8.3 3l-4-4.2 2.3-1.6c-1-1-1.6-1-2.8-1.6-.6-.4-.6-1-1.2-1.5-.5.2-1.8.3-2.4.4-1.6.4-3 .7-4.7 1.4-1.5.4-3.6 1-3.6 2.7zm15.8-7.3c-.3 1.4-1.6 1.7-2.8 2.6l.6.7c.8.4 5 1 6.2 1.3 2.6 0 2.7-1.6 5.8-2l4-.8c3.6-.3 8.6-.5 12-2-1.4-1.8-2.2-1.8-4-2.4-3-.8-6.3-1-9.3 0-3 .8-2.7 2-6.4 2.2l-6 .3z"
              ></path>
            </g>
          </g>
        </svg>
        <div class="text-container">
          <h1 class="number">13</h1>
          <h1 class="text">CLIMATE <br> ACTION</h1>
        </div>
      </div>

      <div class="fade-in1">
        <div class="bg-image">
          <img src="/hero-bg.jpg" alt="" />
        </div>
        <div class="content">
          <div class="tag">
            <p>Waste generated since you arrived</p>
            <p>{{ formatShort(wasteGenerated) }} <span>Tons</span></p>
          </div>
          <div class="tag center">
            <p>Plastic waste generated since you arrived</p>
            <p>{{ formatShort(plasticWaste) }} <span>Tons</span></p>
          </div>
          <div class="tag bottom">
            <p>Total waste generated every year</p>
            <p>{{ formatShort(globalWaste) }} <span>Tons</span></p>
          </div>
        </div>
        <div class="cut-out">
          <a href="#sdgs">
            <CTA label="The SDGs" />
          </a>
        </div>
        <div class="top-cut-out">
          <ul>
            <li>
              The Arctic is expected to have its first ice-free summers by or
              before 2050.
            </li>
            <li>
              Extreme weather events will increase in frequency and intensity.
            </li>
            <li>
              Millions of species at risk due to habitat loss and ocean
              acidification.
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
/* Imports */
import { onMounted, ref } from "vue";
import CTA from "./cta.vue";

import {
  PhBroom,
  PhPlant,
  PhRecycle,
  PhThermometerHot,
} from "@phosphor-icons/vue";

import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay } from "swiper/modules";
import "swiper/css";

import gsap from "gsap";
import { SplitText } from "gsap/all";

/* Mobile menu function */
const mobileMenu = ref(false);
const toggleMenu = () => {
  mobileMenu.value = !mobileMenu.value;
};

const globalWaste = ref(2_010_000_000);
const carbonWaste = ref(1_600_000_000);
const wasteGenerated = ref(0);
const plasticWaste = ref(0);

function formatShort(num) {
  if (num >= 1_000_000_000) return (num / 1_000_000_000).toFixed(2) + "B";
  if (num >= 1_000_000) return (num / 1_000_000).toFixed(2) + "M";
  if (num >= 1_000) return (num / 1_000).toFixed(2) + "K";
  return num.toString();
}

function animateCounter(refVar, target, duration = 2000) {
  let start = 0;
  const stepTime = 10;
  const increment = target / (duration / stepTime);

  const counter = setInterval(() => {
    start += increment;
    if (start >= target) {
      refVar.value = target;
      clearInterval(counter);
    } else {
      refVar.value = Math.floor(start);
    }
  }, stepTime);
}

onMounted(() => {
  const wastePerSecond = 70;
  const plasticPerSecond = 12;

  setInterval(() => {
    wasteGenerated.value += wastePerSecond;
    plasticWaste.value += plasticPerSecond;
  }, 1000);

  animateCounter(globalWaste, globalWaste.value);
  animateCounter(carbonWaste, carbonWaste.value);

  const climateText = new SplitText(".hero h1", { type: "words" });

  const logoAnimationX = window.innerWidth < 1280 ? "-100" : "0";
  const logoAnimationY = window.innerWidth < 1280 ? "0" : "-100";
  const navAnimation = window.innerWidth < 1280 ? "100" : "-100";

  const globeSpin = gsap.to(".svg-globe", {
    rotate: 360,
    repeat: -1,
    duration: 20,
    ease: "none",
    paused: true,
  });

  const heroTimeline = gsap.timeline({
    defaults: { duration: 1, ease: "power3.out" },
    onComplete: () => {
      gsap.to(".tag", {
        y: "+=15", // Move 8px down from its current position
        x: "-=5", // Move 5px left from its current position
        duration: 3, // Take 3 seconds for the movement
        ease: "sine.inOut", // A very smooth, slow ease
        yoyo: true, // Go back and forth
        repeat: -1, // Repeat forever
        repeatDelay: 2, // Wait 2 seconds between each float cycle
        stagger: 0.7, // Stagger the start time for each tag by 0.7s
      });
    },
  });

  heroTimeline
    .from(".fade-in1", {
      y: 25,
      opacity: 0,
      stagger: 0.1,
    })
    .from(
      ".logo",
      {
        x: logoAnimationX,
        y: logoAnimationY,
        opacity: 0,
      },
      "-=0.5"
    )
    .from(
      "nav",
      {
        x: navAnimation,
        opacity: 0,
        stagger: 0.05,
      },
      "<"
    )
    .from(
      ".ctas, .hamburger",
      {
        x: 100,
        opacity: 0,
        stagger: 0.1,
      },
      "<"
    )
    .from(
      ".svg-eye",
      {
        scale: 0.8,
        opacity: 0,
        duration: 1.2,
        ease: "expo.out",
      },
      "-=0.5"
    )
    .from(
      ".svg-globe",
      {
        scale: 0.7,
        opacity: 0,
        duration: 1.2,
        ease: "expo.out",
        onStart: () => globeSpin.play(),
      },
      "-=1.0"
    )
    .from(
      climateText.words,
      {
        y: 25,
        opacity: 0,
        stagger: 0.05,
      },
      "-=1.0"
    )
    .from(
      "h1 svg",
      {
        opacity: 0,
        scale: 0,
        stagger: 0.1,
        ease: "back.out(2)",
      },
      "-=0.5"
    )
    .from(
      ".bg-image",
      {
        scale: 1.1,
        opacity: 0,
        duration: 1.5,
      },
      "-=1.2"
    )
    .from(
      ".tag",
      {
        x: -20,
        opacity: 0,
        stagger: 0.2,
      },
      "-=1.0"
    )
    .from(
      ".cut-out a",
      {
        scale: 0.5,
        opacity: 0,
        duration: 0.7,
      },
      "-=0.5"
    )
    .from(
      ".top-cut-out ul",
      {
        scale: 0.8,
        opacity: 0,
        duration: 0.7,
      },
      "-=0.5"
    );
});
</script>

<style lang="scss">
#hero {
  padding: 15px;
  width: 100%;
  height: 100dvh;
  position: relative;

  .mobile-menu {
    position: absolute;
    top: -100%;
    padding: 0 25px;
    width: calc(100% - 30px);
    height: calc((100vh - 120px) / 2);
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    background: var(--secondary);
    z-index: 10;
    border-radius: 12px;
    transition: 0.3s;
    opacity: 0;
    &.active {
      top: 90px;
      opacity: 1;
    }
    a {
      font-family: var(--alternate-font);
      font-size: 20px;
    }
  }

  header {
    background: var(--secondary);
    padding: 0 15px;
    height: 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-radius: 12px;
    .logo {
      width: 75px;
      height: 100%;
      display: flex;
      justify-content: start;
      align-items: center;
      img {
        width: 80%;
        height: 80%;
        object-fit: contain;
      }
    }
    nav {
      display: none;
      gap: 15px;
      a {
        position: relative;
        font-family: var(--alternate-font);
        transition: 0.2s;
        color: var(--primary);
        &::before {
          content: "";
          position: absolute;
          bottom: 0;
          left: 0;
          width: 0;
          height: 2px;
          background: var(--primary);
          border-radius: 5px;
          transition: 0.2s;
        }
        &:hover {
          &::before {
            width: 100%;
          }
        }
      }
    }
    .ctas {
      display: none;
      gap: 25px;
      .sdg {
        display: flex;
        align-items: center;
        gap: 15px;
        img {
          height: 32px;
          width: auto;
          filter: grayscale(100);
          transition: 0.3s;
          &:hover {
            filter: none;
            transform: scale(1.1);
          }
        }
      }
    }
  }

  .hero {
    margin-top: 15px;
    height: calc(100vh - 105px);
    display: flex;
    flex-direction: column;
    gap: 15px;

    > :nth-child(1) {
      position: relative;
      height: 50%;
      background: var(--primary);
      border-radius: 12px;
      overflow: hidden;
      .svg-eye,
      .svg-globe {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translateX(-50%) translateY(-50%);
      }
      .svg-eye {
        width: 95%;
        display: none;
      }
      .svg-globe {
        width: 150%;
        circle {
          stroke-width: 0;
        }
      }
      .text-container {
        position: absolute;
        top: 0;
        left: 0;
        padding: 15px;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 15px;
        h1 {
          font-weight: bold;
          font-size: 25px;
          color: #f7f7f7;
          /* svg {
            color: var(--accent);
          }
          span {
            text-decoration: underline;
            color: var(--accent);
          } */
        }
        .number {
          font-size: 80px;
          color: var(--accent);
        }
      }
    }

    > :nth-child(2) {
      position: relative;
      height: 50%;
      background: var(--accent);
      border-radius: 12px;
      overflow: hidden;

      .bg-image {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      .content {
        position: relative;
        width: 100%;
        height: 100%;
        padding: 15px;
        z-index: 1;
        background: #00000050;
        .tag {
          display: flex;
          flex-direction: column;
          gap: 5px;
          &.center {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translateX(-50%) translateY(-50%);
          }
          &.bottom {
            position: absolute;
            bottom: 15px;
            right: 25px;
          }
          > :nth-child(1) {
            &::before {
              content: "";
              position: absolute;
              top: 50%;
              left: -20px;
              transform: translateY(-50%);
              width: 10px;
              height: 10px;
              background: var(--accent);
              border-radius: 50%;
              outline: 1px solid var(--accent);
              outline-offset: 4px;
            }
          }
          p {
            position: relative;
            left: 15px;
            padding: 5px;
            width: max-content;
            font-weight: bold;
            font-size: 12.5px;
            color: var(--accent);
            border: 1px solid var(--accent);
            border-radius: 20px;
            span {
              color: var(--accent);
            }
          }
        }
      }
      .cut-out,
      .top-cut-out {
        display: none;
      }
    }
  }
}

@media (min-width: 600px) and (max-width: 1279px) {
  #hero {
    header {
      padding: 0 25px;
      nav {
        display: flex;
      }
      .hamburger {
        display: none;
      }
    }
    .hero {
      > :nth-child(1) {
        .svg-eye {
          display: block;
        }
        .svg-globe {
          width: 40%;
          circle {
            stroke-width: 14px;
          }
        }
        .text-container {
          .text {
            font-size: 40px;
          }
          .number {
            font-size: 120px;
          }
        }
      }
      > :nth-child(2) {
        .content {
          .tag {
            &.center {
              top: 25%;
              left: 75%;
            }
            &.bottom {
              bottom: 50px;
              right: 50%;
            }
          }
        }
      }
    }
  }
}

@media (min-width: 1280px) {
  #hero {
    header {
      padding: 0 25px;
      nav {
        display: flex;
        order: -1;
        width: 40%;
      }
      .ctas {
        width: 40%;
        display: flex;
        justify-content: end;
      }
      .hamburger {
        display: none;
      }
    }
    .hero {
      flex-direction: row;
      > :nth-child(1) {
        width: 50%;
        height: 100%;
        .svg-eye {
          top: 65%;
          display: block;
        }
        .svg-globe {
          top: 65%;
          width: 40%;
          circle {
            stroke-width: 14px;
          }
        }
        .text-container {
          left: 25px;
          height: 25%;
          justify-content: start;
          .text {
            font-size: 40px;
          }
          .number {
            font-size: 120px;
          }
        }
      }
      > :nth-child(2) {
        width: 50%;
        height: 100%;
        .content {
          .tag {
            position: absolute;
            top: 30%;
            &.center {
              top: 50%;
              left: 75%;
            }
            &.bottom {
              top: unset;
              bottom: 25%;
              right: 50%;
            }
          }
        }
        .cut-out {
          position: absolute;
          bottom: 0;
          right: 0;
          padding: 8px 0 0 8px;
          display: block;
          z-index: 5;
          background: white;
          border-top-left-radius: 12px;
          .button {
            border-radius: 4px;
            &:hover {
              transform: scale(1);
            }
          }
          &::after {
            content: "";
            position: absolute;
            top: -36px;
            right: 0;
            width: 36px;
            height: 36px;
            border-bottom-right-radius: 12px;
            box-shadow: 5px 5px white;
          }
          &::before {
            content: "";
            position: absolute;
            bottom: 0;
            left: -36px;
            width: 36px;
            height: 36px;
            border-bottom-right-radius: 12px;
            box-shadow: 10px 10px white;
          }
        }
        .top-cut-out {
          position: absolute;
          top: 0;
          left: 0;
          padding: 0 10px 10px 0;
          display: block;
          background: white;
          z-index: 5;
          border-bottom-right-radius: 12px;
          &::after {
            content: "";
            position: absolute;
            top: 0;
            right: -36px;
            width: 36px;
            height: 36px;
            border-top-left-radius: 12px;
            box-shadow: -10px -10px white;
          }
          &::before {
            content: "";
            position: absolute;
            bottom: -36px;
            left: 0;
            width: 36px;
            height: 36px;
            border-top-left-radius: 12px;
            box-shadow: -10px -10px white;
          }
          ul {
            list-style: disc;
            padding: 10px 10px 10px 25px;
            background: var(--secondary);
            border-radius: 6px;
            li {
              font-size: 12.5px;
              color: var(--primary);
              &::marker {
                color: var(--accent);
              }
            }
          }
        }
      }
    }
  }
}
</style>

<style scoped>
.hamburger {
  cursor: pointer;
}

.hamburger input {
  display: none;
}

.hamburger svg {
  height: 42px;
  transition: transform 600ms cubic-bezier(0.4, 0, 0.2, 1);
}

.line {
  fill: none;
  stroke: white;
  stroke-linecap: round;
  stroke-linejoin: round;
  stroke-width: 2;
  transition: stroke-dasharray 600ms cubic-bezier(0.4, 0, 0.2, 1),
    stroke-dashoffset 600ms cubic-bezier(0.4, 0, 0.2, 1);
}

.line-top-bottom {
  stroke-dasharray: 12 63;
}

.hamburger input:checked + svg {
  transform: rotate(-45deg);
}

.hamburger input:checked + svg .line-top-bottom {
  stroke-dasharray: 20 300;
  stroke-dashoffset: -32.42;
}
</style>