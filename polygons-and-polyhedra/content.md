# Polygons and Polyhedra

stage: foundations
description: Shapes and geometry is everywhere around us, is nature, architecture, technology or science. Here you will learn about angels, polygons, tessellations and polyhedra.
icon: courses/f-polyhedra.png
hero: images/hero.jpg
tile: images/og-tile.jpg

---{#polygon1}

## Polygons

You’ve already learned about points, lines, angles, shapes and other objects in
geometry. A __polygon__ is any shape which is made up only of straight lines. A
square, for example, is a polygon, but a circle is not. Select all of these
shapes which are polygons:

  .set-picker
    .row.padded-thin
      .set-item.valid: svg(width=120, height=120): polygon(points="12,73 47,12 108,47 73,108", fill="#c1272d")
      .set-item: svg(width=120, height=120): circle(cx="60", cy="60", r="44", fill="#f15a24")
      .set-item.valid: svg(width=120, height=120): polygon(points="93,93 47,105 14,72 26,26 72,14 105,47", fill="#fbb03b")
      .set-item.valid: svg(width=120, height=120): polygon(points="93,73 93,46 81,46 81,19 38,19 38,46 26,46 26,73 13,73 13,100 106,100 106,73", fill="#d9e021")
      .set-item: svg(width=120, height=120): path(d="M59,18c-19,0-35,16-35,35v46h71V54C94,34,78,18,59,18z", fill="#8cc63f")
      .set-item: svg(width=120, height=120): path(d="M96,12L13,26l14,82C74,101,104,58,96,12z", fill="#009245")
      .set-item: svg(width=120, height=120): path(d="M16,26c12-14,41-10,65,9s33,47,22,61s-40,10-64-9S5,40,16,26z", fill="#00a99d")
      .set-item.valid: svg(width=120, height=120): polygon(points="115,60 52,100 13,64 55,5 65,40", fill="#0071bc")
      .set-item.valid: svg(width=120, height=120): polygon(points="36,102 13,51 54,13 103,41 92,96 ", fill="#1b1464")
      .set-item.valid: svg(width=120, height=120): polygon(points="101,26 88,57 106,86 72,83 50,109 43,76 11,63 40,46 43,12 68,34", fill="#93278f")
    p.text-center: button.btn.btn-bounce.btn-small Check…

---{#polygon2}

If all the sides of a polygon have the same length, it is called a
__regular polygon__. Select all of these shapes which are regular polygons:

  .set-picker
    .row.padded-thin
      .set-item.valid: svg(width=120, height=120): polygon(points="36,102 13,51 54,13 103,41 92,96 ", fill="#c1272d")
      .set-item: svg(width=120, height=120): polygon(points="90,7 109,108 5,87 27,23", fill="#fbb03b")
      .set-item.valid: svg(width=120, height=120): polygon(points="93,93 14,72 72,14", fill="#8cc63f")
      .set-item.valid: svg(width=120, height=120): polygon(points="93,93 47,105 14,72 26,26 72,14 105,47", fill="#00a99d")
      .set-item: svg(width=120, height=120): polygon(points="115,60 52,100 13,64 55,5 65,40", fill="#1b1464")
    p.text-center: button.btn.btn-bounce.btn-small Check…

{.subsection(data-needs="setpicker")}
Regular triangles are often called __equilateral triangles__, and regular
quadrilaterals (4-gons) are often called __squares__.

// Finally, the sides of a polygon are called __edges__, and the points are
// called __vertices__. However this is terminology for now!

---{#triangles}

## Angles in Triangles

Every triangle has three __internal angles__ – angles at every vertex on the
inside. In this diagram you can move the vertices and see what happens to the
internal angles. Try making all angles as large as possible, or as small as
possible, or as equal as possible.

  .geopad
    svg
      path.geo-angle(x-d="${svgAngle(a,b,c,50)}")
      path.geo-angle.m-blue(x-d="${svgAngle(b,c,a,50)}")
      path.geo-angle.m-green(x-d="${svgAngle(c,a,b,50)}")
      path.geo-line(x-d='${svgLine(a,b)}')
      path.geo-line(x-d='${svgLine(a,c)}')
      path.geo-line(x-d='${svgLine(b,c)}')
      polygon.geo-polygon(x-points="${svgPolygon(a,b,c)}")
      circle.geo-vertex(x-cx="${a.x}", x-cy="${a.y}", r="10")
      circle.geo-vertex(x-cx="${b.x}", x-cy="${b.y}", r="10")
      circle.geo-vertex(x-cx="${c.x}", x-cy="${c.y}", r="10")
    .angle-values
      .angle-value.m-red ${deg(c,a,b)}°
      .angle-value.m-blue ${deg(a,b,c)}°
      .angle-value.m-green ${deg(b,c,a)}°
      select.angle-value
        option(value="max") Largest angle:
        option(value="min") Smallest angle:
        option(value="prod") Product of angles:
        option(value="sum") Sum of angles:
      .angle-value ${selected(a,b,c)}°

---{#triangleProof}

  .row
    .grow
      p In #[em any] triangle, the sum of the internal angles is always #[+input(180)]°.
      p This is one of the most fundamental results in geometry and it is not difficult to see why.
      p.subsection(data-needs="blank-0") First we take one of the sides of the triangle and draw a parallel line through the remaining vertex.
      p.subsection Now we can shift the green and blue angles #[em up one level], because they are #[+blank("corresponding|opposite|alternating")] angles.
      p.subsection(data-needs="blank-0 blank-1") Finally we can flip the red angle over,  because they are #[+blank("opposite|corresponding|alternating")] angles.
      p.subsection(data-needs="blank-0 blank-1 blank-2") Now the #[strong.m-blue blue], #[strong.m-red red] and #[strong.m-green green] angle form exactly one semicircle, which is 180°. Like before, you can move the vertices in the diagram to see that this works for #[em any] triangle.
    .geopad(style="width:300px")
      svg(style="height:360px")
        // path(d="${angle(a,b,c)}", class='geo-angle m-red faded')
        // g(transform="${slide>3?'rotate(180deg)':''}")
        // circle(cx="${a[0]}", cy="${a[1]}", r="30")
        path.geo-angle(x-d="${svgAngle(a,b,c,50)}")
        path.geo-angle.m-blue(x-d="${svgAngle(b,c,a,50)}")
        path.geo-angle.m-green(x-d="${svgAngle(c,a,b,50)}")
        path.geo-angle.opposite(x-d="${svgOppositeAngle(a,b,c,50)}", style="display: none;")
        path.geo-angle.m-blue.corresponding(x-d="${svgCorrespondingAngle(b,c,a,50,a)}", style="display: none;")
        path.geo-angle.m-green.corresponding(x-d="${svgCorrespondingAngle(c,a,b,50,a)}", style="display: none;")
        path.geo-line(x-d='${svgLine(a,b)}')
        path.geo-line(x-d='${svgLine(a,c)}')
        path.geo-line(x-d='${svgLine(b,c)}')
        path.geo-line.parallel(x-d='${svgLineThrough(b,c,a)}', style="display: none;")
        polygon.geo-polygon(x-points="${svgPolygon(a,b,c)}")
        circle.geo-vertex(x-cx="${a.x}", x-cy="${a.y}", r="10")
        circle.geo-vertex(x-cx="${b.x}", x-cy="${b.y}", r="10")
        circle.geo-vertex(x-cx="${c.x}", x-cy="${c.y}", r="10")

---

Since we know the sum of the angles in every triangle, we can also work out the
size of a missing angle.

  .box.problem-box
    .box-title: h3 Find the missing angles
    .box-body: p.todo Exercises under development…

---{#quadrilateral.gloss(quadrilateral)}

## Angles in Polyhedra

Next, let’s have a look at quadrilaterals. 

  .geopad
    svg
      path.geo-line(x-d='${svgLine(a,b)}')
      path.geo-line(x-d='${svgLine(b,c)}')
      path.geo-line(x-d='${svgLine(c,d)}')
      path.geo-line(x-d='${svgLine(a,d)}')
      path.geo-angle(x-d="${svgAngle(a,b,d,50,true)}")
      path.geo-angle.m-blue(x-d="${svgAngle(b,c,a,50,true)}")
      path.geo-angle.m-green(x-d="${svgAngle(c,d,b,50,true)}")
      path.geo-angle.m-yellow(x-d="${svgAngle(d,a,c,50,true)}")
      polygon.geo-polygon(x-points="${svgPolygon(a,b,c,d)}")
      circle.geo-vertex(x-cx="${a.x}", x-cy="${a.y}", r="10")
      circle.geo-vertex(x-cx="${b.x}", x-cy="${b.y}", r="10")
      circle.geo-vertex(x-cx="${c.x}", x-cy="${c.y}", r="10")
      circle.geo-vertex(x-cx="${d.x}", x-cy="${d.y}", r="10")
    .angle-values
      .angle-value.m-red ${deg(b,a,d)}°
      .angle-value.m-blue ${deg(c,b,a)}°
      .angle-value.m-green ${deg(d,c,b)}°
      .angle-value.m-yellow ${deg(a,d,c)}°
      select.angle-value
        option(value="max") Largest angle:
        option(value="min") Smallest angle:
        option(value="prod") Product of angles:
        option(value="sum") Sum of angles:
      .angle-value ${selected(a,b,c,d)}°

It seems that the sum of the internal angles is always <360>°.

---{#polygonsangle}

This is no only a full circle rotation, it is also twice the sum of triangles.
And this is because we can split every quadrilateral into two triangles.

  .row.padded
    .grow(style="width:120px"): include svg/square.svg
    .grow.pentagon(style="width:120px; visibility: hidden"): include svg/pentagon.svg
    .grow.hexagon(style="width:120px; visibility: hidden"): include svg/hexagon.svg
    .grow.heptagon(style="width:120px; visibility: hidden"): include svg/heptagon.svg

The same, of course, also works for larger polygons. We can split a pentagon
into <3> triangles, so its internal angle sum is <540>°. And we can split a
hexagon into <4> triangles, so its internal angle sum is <720>°.

In general, a polygon with ${fn1(x)}{x|2|2,12,1} sides will have an internal
angle sum of 180° × ${fn2(x)}.

---

Remember that in regular polygons, all sides have the same length and all angles
are all the same size. Therefore we can calculate the size of a single internal
angle in a regular polygon:

{.text-center} angle = #[mfrac #[mrow <sum of all angles|number of angles>]]#[mrow #[+blank("number of angles|sum of all angles")]]] = #[+frac('180° × (<em>x</em> – 2)', '<em>x</em>')] = 180° – #[+frac('360°','<em>x</em>')].

In particular, the sum of a regular polygon with ${x}{x|6|3,12,1} sides is 180°
– #[mfrac.inline #[mrow 360°]#[mrow #[+var x]]] = #[+var Math.round(180-360/x)]°.

---

## Quadrilaterals

Quadrilaterals are polygons with four sides. There are several special kinds of
quadrilaterals:

  table.quadrilaterals
    tr
      td
      td(colspan=2)
        include svg/quadrilaterals/trapezium.svg
        p.caption If a pair of opposite sides are parallel, we have a #[strong Trapezium].
    tr
      td
      td(colspan=2)
        .line
        include svg/quadrilaterals/parallelogram.svg
        p.caption If #[em both] pairs of opposite sides are parallel, we have a #[strong Parallelogram].
      td(colspan=2)
        include svg/quadrilaterals/kite.svg
        p.caption If, instead, two pairs of #[em adjacent] sides have the same length, we have a #[strong Kite].
    tr
      td(colspan=2)
        .line.left
        include svg/quadrilaterals/rectangle.svg
        p.caption If all four angles are right angles (90°), we have a #[strong Rectangle].
      td(colspan=2)
        .line.left
        .line.right
        include svg/quadrilaterals/rhombus.svg
        p.caption Or if all four #[em sides] have the same length, we have a #[strong Rhombus].
    tr
      td
      td(colspan=2)
        .line.left
        .line.right
        include svg/quadrilaterals/square.svg
        p.caption Finally, if all angles are 90° #[em and] all sides have the same length, we have a #[strong square].

---{#classifyquadriateral.gloss(trapezium parallelogram kite rectangle rhombus)}

Any quadrilaterals could fall into more than one of these categories. Let’s have
a look at a simple example:

  .row
    div(style="width: 200px")
      include svg/quadrilaterals/classify.svg
    .grow
      p This shape is clearly a #[+blank('rhombus|trapezium|square')], because all four of its #[+blank('sides|angles')] have the same length.
      p.subsection(data-needs="blank-0 blank-1") But top and bottom pairs of adjacent sides also #[em each] have the same length. Therefore this is also a #[+blank('kite|rectangle')].
      p.subsection(data-needs="blank-2") And both pairs of opposite sides are parallel, so this is also a #[+blank('parallelogram|square')].
      p.subsection(data-needs="blank-3") Finally, if both pairs of sides are parallel, then #[em one] pair of sides must also be parallel. Therefore we also have a #[+blank('trapezium|rectangle')].

  p.subsection(data-needs="blank-4") To avoid this kind of ambiguity when identifying quadrilaterals, we usually only use the #[em most specific] one – or the type furthest down in the tree diagram above. In the above example that would be a #[+blank('rhombus|kite|parallelogram|trapezium')].

---

  .box.problem-box
    .box-title: h3 Identify the Quadrilateral
    .box-body: p.todo Exercises under development…

---

  .row
    .grow
      p We often need to calculate the area of quadrilaterals. The area of a square is simply its width squared. The area of a rectangle is the #[+blank('product|sum')] of its width and its height.
      p For other quadrilaterals, we first have to try to “convert” them into rectangles.
    div(style="width: 250px"): include svg/quadrilaterals/area.svg

---

### Parallelogram

  .row
    div(style="width: 260px; margin-top: -20px")
      include svg/quadrilaterals/area-parallelogram.svg
    .grow
      p Notice how the overlap on the left is exactly the same as the gap on the right. Therefore the area of the #[strong.m-blue blue parallelogram] is #[+blank('the same as|smaller than|larger than')] the area of the #[strong.m-red red rectangle]. This means that the area of any parallelogram is simply
      p.text-center #[strong.i.m-green base] × #[strong.i.m-yellow height].

---

### Kite and Rhombus

  .row
    div(style="width: 260px; margin-top: -20px")
      include svg/quadrilaterals/area-kite.svg
    .grow
      p Each the four smaller rectangles are exactly half blue. Therefore the area of the #[strong.m-blue blue kite] is half the area of the #[strong.m-red red rectangle]. In other words, the area of a kite or rhombus is always
      p.text-center #[+frac(1, 2)] #[strong.i.m-green width] × #[strong.i.m-yellow height].

---

### Trapezium

  .row
    div(style="width: 260px")
      include svg/quadrilaterals/area-trapezium.svg
    .grow
      p Notice how the gaps on the left and right are each exactly as big as the overlap on that side. The width of the #[strong.m-red red rectangle] is the average of the widths of the top side and the bottom side of the #[strong.m-blue blue trapezium]. Therefore the area of a trapezium is
      p.text-center #[mfrac #[mrow #[strong.i.m-green top] + #[strong.i.m-green bottom]]#[mrow 2]] × #[strong.i.m-yellow height].

---

  .box.problem-box
    .box-title: h3 Area of Quadrilaterals
    .box-body: p.todo Exercises under development…

//- section
  TODO More on Quadrilaterals coming soon…
  Parallelogram diagonals bisect each other
  Parallelogram opposite angles are equal, adjacent add up to 180°
  Rhombus diagonals are perpendiucular bisectors
  Cyclic quadrilaterals

---{#parallelograms}

If we connect the centers of the four sides of a quadrilateral, we get
<another quadrilateral|a triangle|a rectangle>. Try to move the vertices of the
outer quadrilateral to change the shape on the inside.

  .geopad
    svg
      polygon.geo-polygon(x-points="${svgPolygon(a,b,c,d)}")
      polygon.geo-polygon(x-points="${svgPolygon(between(a,b),between(b,c),between(c,d),between(d,a))}", style="fill: #b30469; stroke: #b30469; stroke-width: 3px; fill-opacity: 0.3")
      circle.geo-vertex(x-cx="${a.x}", x-cy="${a.y}", r="10")
      circle.geo-vertex(x-cx="${b.x}", x-cy="${b.y}", r="10")
      circle.geo-vertex(x-cx="${c.x}", x-cy="${c.y}", r="10")
      circle.geo-vertex(x-cx="${d.x}", x-cy="${d.y}", r="10")
      circle(x-cx="${(a.x + b.x)/2}", x-cy="${(a.y + b.y)/2}", r="6" style="fill: #b30469")
      circle(x-cx="${(b.x + c.x)/2}", x-cy="${(b.y + c.y)/2}", r="6" style="fill: #b30469")
      circle(x-cx="${(c.x + d.x)/2}", x-cy="${(c.y + d.y)/2}", r="6" style="fill: #b30469")
      circle(x-cx="${(d.x + a.x)/2}", x-cy="${(d.y + a.y)/2}", r="6" style="fill: #b30469")

  .subsection
    p It looks like the quadrilateral on the inside is always a #[+blank('parallelogram|trapezium|rectangle')]!
    p.todo Explanation coming soon…

---{.gloss(tessellation)}

## Tessellations

Polygons appear everywhere in nature. They are especially useful if you want to
tile a large area, because you can fit polygons together without any gaps or
overlaps – these patterns are called __tessellations__.

  .row
    div(style="width: 200px")
      x-media(lightbox, credit="© Depositphotos / Irochka", src="/resources/polygons-and-polyhedra/images/tessellations/honeycomb.jpg", width="200", height="200")
      p.caption Hexagonal honeycomb
    div(style="width: 200px")
      x-media(lightbox, credit="© Depositphotos / Tiukay", src="/resources/polygons-and-polyhedra/images/tessellations/snake.jpg", width="200", height="200")
      p.caption Sinaloan milk snake skin
    div(style="width: 200px")
      x-media(lightbox, credit="© Depositphotos / SuradechK", src="/resources/polygons-and-polyhedra/images/tessellations/leaf.jpg", width="200", height="200")
      p.caption Cellular structure of leafs
    div(style="width: 200px")
      x-media(lightbox, credit="Chmee2, via Wikipedia", src="/resources/polygons-and-polyhedra/images/tessellations/causeway.jpg", width="200", height="200")
      p.caption Basalt columns at Giant's Causeway in Northern Ireland
    div(style="width: 200px")
      x-media(lightbox, credit="© Depositphotos / Kostia777", src="/resources/polygons-and-polyhedra/images/tessellations/pineapple.jpg", width="200", height="200")
      p.caption Pineapple skin
    div(style="width: 200px")
      x-media(lightbox, credit="© Depositphotos / cbenjasuwan", src="/resources/polygons-and-polyhedra/images/tessellations/tortoise.jpg", width="200", height="200")
      p.caption Shell of a tortoise

And, of course, humans have copied many of these natural patterns in
architecture and technology:

  .row
    div(style="width: 200px")
      x-media(lightbox, credit="© Depositphotos / kelifamily", src="/resources/polygons-and-polyhedra/images/tessellations/pavement.jpg", width="200", height="200")
      p.caption Rectangular pavement pattern
    div(style="width: 200px")
      x-media(lightbox, src="/resources/polygons-and-polyhedra/images/tessellations/greenhouse.jpg", width="200", height="200")
      p.caption Greenhouse at the Eden project
    div(style="width: 200px")
      x-media(lightbox, credit="Andrew Dunn, via Wikipedia", src="/resources/polygons-and-polyhedra/images/tessellations/alhambra.jpg", width="200", height="200")
      p.caption Mosaic at Alhambra
    div(style="width: 200px")
      x-media(lightbox, credit="Chmee2 via Wikipedia", src="/resources/polygons-and-polyhedra/images/tessellations/museum.jpg", width="200", height="200")
      p.caption Great Court Roof at the British Museum in London
    div(style="width: 200px")
      x-media(lightbox, credit="© Patrick Boland, via archinect.com", src="/resources/polygons-and-polyhedra/images/tessellations/cellular.jpg", width="200", height="200")
      p.caption Cellular tessellation pavilion in Sydney
    div(style="width: 200px")
      x-media(credit="© M. C. Escher", src="/resources/polygons-and-polyhedra/images/tessellations/escher.jpg", width="200", height="200")
      p.caption Study of Regular Division of the Plane with Reptiles, M. C. Escher

  // TODO Carbon Nanotube
  // application: https://en.wikipedia.org/wiki/Carbon_nanotube
  // https://en.wikipedia.org/wiki/File:Types_of_Carbon_Nanotubes.png
  // https://commons.wikimedia.org/wiki/File:FlyingThroughNanotube.png

section#drawing
  p Here you can create your own tessellations with regular polygons. See if there are any shapes that tessellate well or not at all, and try to create interesting patterns.

  .tessellation-canvas.frame.fill: svg
  //- TODO rotate, add new, delete, snap to corner, export to png, clear canvas, save to db

section#possible
  p When creating tessellations with regular polygons, you'll have noticed that some kinds of polygons tessellate easily, while others don’t tessellate at all.

  .row
    div(style="width: 160px")
      include svg/triangles.svg
      p.caption Triangles #[+blank("tessellate|don’t tessellate")] because 6 × 60° = 360°.
    div(style="width: 160px")
      include svg/squares.svg
      p.caption Squares #[+blank("tessellate|don’t tessellate")] because 4 × 90° = 360°.
    div(style="width: 160px")
      include svg/pentagons.svg
      p.caption Pentagons #[+blank("don’t tessellate|tessellate")] because multiples of 108° don't add up to 360°.
    div(style="width: 160px")
      include svg/hexagons.svg
      p.caption Hexagons #[+blank("tessellate|don’t tessellate")] because 3 × 120° = 360°.

  p This has to do with the size of their internal angles, which we leaned to calculate before. If you can make multiples of their internal angle add up to #[+input(360)]°, the shape will tessellate. Otherwise there will either be a gap or an overlap.

---

You can also make tessellations out of multiple different kinds of regular
polygons, provided their combined internal angles make 360°:

  x-gallery(slide-width="520")
    div
      include svg/tessellations/tessellation_1.svg
      p.caption equilateral triangles and squares
    div
      include svg/tessellations/tessellation_3.svg
      p.caption equilateral triangles and squares
    div
      include svg/tessellations/tessellation_4.svg
      p.caption equilateral triangles and regular hexagons
    div
      include svg/tessellations/tessellation_5.svg
      p.caption equilateral triangles and regular hexagons
    div
      include svg/tessellations/tessellation_2.svg
      p.caption equilateral triangles, squares and regular hexagons
    div
      include svg/tessellations/tessellation_6.svg
      p.caption squares and octagons (8-gons)
    div
      include svg/tessellations/tessellation_7.svg
      p.caption equilateral triangles and dodecagons (12-gons)
    div
      include svg/tessellations/tessellation_8.svg
      p.caption equilateral triangles, squares and dodecagons

Notice, however, that none of these tessellations contain a regular
<pentagon|hexagon|octagon>…

---

And of course we can make tessellations out of non-regular polygons as well:

  .row
    div(style="width: 320px")
      p.todo Interactive diagram coming soon…
    .grow: p Triangles always tessellate. Their internal angle sum is #[+input(180)]°, so if we use every angle twice at a vertex, we get 360°.
    div(style="width: 320px")
      p.todo Interactive diagram coming soon…
    .grow: p Quadrilaterals always tessellate. Their internal angle sum is #[+input(360)]°, so if we use every angle at a vertex, we get 360°.
    div(style="width: 320px")
      p.todo Diagram coming soon…
    .grow: p Pentagons sometimes tessellate, but only if they have particular shapes.

---

Many artists came up with much more complicated tessellations, most famously
[M. C. Escher](.bio(escher)). Here are a few examples:

  .img-block
    .row
      .grow.shrink(style="width: 226px; flex-grow: 2.17; flex-shrink: 2.17"): x-media(credit="© M. C. Escher", src="/resources/polygons-and-polyhedra/images/escher/mirror.jpg", width="509", height="315")
      .grow.shrink(style="width: 104px"): x-media(credit="© M. C. Escher", src="/resources/polygons-and-polyhedra/images/escher/knights.jpg", width="234", height="315")
    .row
      .grow(style="width: 161px; flex-grow: 1.15; flex-shrink: 1.15"): x-media(credit="© M. C. Escher", src="/resources/polygons-and-polyhedra/images/escher/reptiles.jpg", width="397", height="346")
      .grow(style="width: 140px"): x-media(credit="© M. C. Escher", src="/resources/polygons-and-polyhedra/images/escher/sky_water.jpg", width="346", height="346")
    p.caption(style="max-width: 500px; margin: 0 auto;") #[em Magic Mirror] (top left), #[em Regular Division of the Plane III] (top right), #[em Reptiles] (bottom left) and #[em Sky and Water I] (bottom right) were all created by M. C. Escher.

---{#penrose(.gloss(penrose)}

All the tessellations we saw so far have one thing in common: they are
_periodic_. This means that they consist of a regular pattern that is repeated
again and again. They can continue forever in all directions and they will look
the same everywhere.

In the 1970s, the English mathematician [Sir Roger Penrose](.bio(penrose))
discovered _non-periodic_ tessellations – they still continue infinitely in all
directions, but will _never_ look exactly the same. These are called __Penrose
tilings__, and you only need a few different kinds of polygons to create one:

  .img-block
    include svg/penrose.svg
    x-slider(steps=100, style="max-width: 400px; margin: 24px auto")
    p.caption Move the slider to reveal the underlying structure of this tessellation. Notice how you have the same patterns at various scales: the small yellow pentagons, blue stars, orange rhombi and green ‘ships’ appear in their original size, in a #[strong.blue slightly larger size] and an #[strong.red even larger size]. This #[em self-similarity] can be used to prove that this Penrose tiling is non-periodic.

---{.gloss(polyhedron face)}

## Polyhedra

Up to now we have looked at what you can do with polygons in a flat,
two-dimensional world. We can also connect polygons to form three-dimensional
solids – these are called __Polyhedra__.

The sides of a polyhedron are called __faces__, the lines where faces meet are
called __edges__, and the corners where __edges__ meet are called vertices.

{.todo} Diagrams and Euler’s Formula coming soon…

// There are countless more polyhedra: some looking like stars, some consisting
// of non-regular polygons, and some having holes inside.

// Notice that the number of faces plus the number of vertices always seems to
// be 2 more that the number of edges. In other words, F + V = E + 2. This
// formula was discovered by Leonhard Euler (1707 – 1783). We have just shown
// that it works for all Platonic solids, but in fact it is true for any
// polyhedron. There is a very similar formula for the number of faces, edges
// and vertices of planar graphs.

---{.gloss(platonic)}

## Platonic Solids

Just like we defined _regular polygons_ as particularly symmetric polygons, we
can create particularly “regular” polyhedra – for example, only using just a
single kind of regular polygon:

To create a 3-dimensional object, we need at least <3> faces to meet at every
vertex. Let’s start with equilateral triangles:

  table.plato.subsection(data-needs="blank-0")
    tr
      td(style="width: 80px"): include svg/platonic/triangle-1.svg
      td(style="width: 80px"): x-media(width="80", height="80", src="/resources/polygons-and-polyhedra/images/polyhedra/tetrahedron.gif")
      td: p We can create a polyhedron where three equilateral triangles meet at every vertex. The result is called a #[strong Tetrahedron].
    tr
      td: include svg/platonic/triangle-2.svg
      td: x-media(width="80", height="80", src="/resources/polygons-and-polyhedra/images/polyhedra/octahedron.gif")
      td: p If four triangles meet at every vertex, we get a different polyhedron called #[strong Octahedron].
    tr
      td: include svg/platonic/triangle-3.svg
      td: x-media(width="80", height="80", src="/resources/polygons-and-polyhedra/images/polyhedra/icosahedron.gif")
      td: p If five triangles meet at every vertex, we get another polyhedron called #[strong Icosahedron].
    tr(style="background: #eee")
      td: include svg/platonic/triangle-4.svg
      td
      td: p If six triangles meet at every vertex we don’t get a polyhedron: just a flat #[+blank('tessellation|angle|quadrilateral')].
    tr(style="background: #eee")
      td(colspan=3): p We always need a #[+blank('gap|overlap')] to create a 3-dimensional shape. Therefore seven or more triangles at every vertex also can’t produce new polyhedra.

---

We can do the same with squares:

  table.plato
    tr
      td(style="width: 80px"): include svg/platonic/square-1.svg
      td(style="width: 80px"): x-media(width="80", height="80", src="/resources/polygons-and-polyhedra/images/polyhedra/cube.gif")
      td: p If three squares meet at every vertex, we get a #[strong cube], sometimes also called #[em Hexahedron].
    tr(style="background: #eee")
      td: include svg/platonic/square-2.svg
      td
      td: p If four squares meet at every vertex, we get another tessellation. Like above, five or more squares also won’t work.

---

Next, let’s try pentagons:

  table.plato
    tr
      td(style="width: 80px"): include svg/platonic/pentagon-1.svg
      td(style="width: 80px"): x-media(width="80", height="80", src="/resources/polygons-and-polyhedra/images/polyhedra/dodecahedron.gif")
      td: p If three pentagons meet at every vertex, we get a polyhedron called #[strong Dodecahedron].
    tr(style="background: #eee")
      td(style="width: 80px"): include svg/platonic/pentagon-2.svg
      td
      td: p Like above, four or more pentagons #[+blank('don’t work|are possible')] because there is no gap we can fold.

---

And similarly for hexagons:

  table.plato
    tr(style="background: #eee")
      td(style="width: 80px"): include svg/platonic/hexagon.svg
      td: p If three hexagons meet at every vertex we get a flat tessellation but no polyhedron. And again, four or more hexagons also don’t work.

---

The same also happens for all regular polygons with more than six sides. They
don’t tessellate, and we certainly don’t get any 3-dimensional polygons.

Thus, there are <5> different polyhedra consisting of just one kind of
<regular polygon|triangle|polygon>. These are called __Platonic Solids__, named
after the Greek philosopher [Plato](.bio(plato)) who discovered them. Their
individual names are derived from the Greek name for their number of faces:
“tetra”, for example, means “four”.

---

Plato believed that all matter in the Universe consists of four elements: air,
earth, water and fire, and that these correspond to different Platonic solids.
The fifth, he thought, was the shape of the entire Universe. Today we know that
there are more than 100 elements which consist of spherical atoms, not
polyhedra.

Try to fill in the following table with properties about the platonic solids:

  table
    tr
      td: strong Tetrahedron
      td: strong Cube
      td: strong Octahedron
      td: strong Dodecahedron
      td: strong Icosahedron
    tr
      td: x-media(width="100", height="100", src="/resources/polygons-and-polyhedra/images/polyhedra/tetrahedron.gif")
      td: x-media(width="100", height="100", src="/resources/polygons-and-polyhedra/images/polyhedra/cube.gif")
      td: x-media(width="100", height="100", src="/resources/polygons-and-polyhedra/images/polyhedra/octahedron.gif")
      td: x-media(width="100", height="100", src="/resources/polygons-and-polyhedra/images/polyhedra/dodecahedron.gif")
      td: x-media(width="100", height="100", src="/resources/polygons-and-polyhedra/images/polyhedra/icosahedron.gif")
    tr
      td Fire
      td Earth
      td Air
      td The Universe
      td Water
    tr
      td #[+input(4)] Faces#[br]#[+input(4)] Vertices#[br]#[+input(6)] Edges
      td #[+input(6)] Faces#[br]#[+input(8)] Vertices#[br]#[+input(12)] Edges
      td #[+input(8)] Faces#[br]#[+input(6)] Vertices#[br]12 Edges
      td #[+input(12)] Faces#[br]20 Vertices#[br]30 Edges
      td #[+input(20)] Faces#[br]12 Vertices#[br]30 Edges

---

Notice how the number of faces and vertices are #<swapped around|the same> for
cube an octahedron, and dodecahedron and icosahedron, while the number of edges
<stays the same|are different>. These pairs of Platonic solids are called
__dual solids__.

We can even turn one into each other, by “replacing” every face with a vertex,
and vice versa:

  .row
    .grow: x-img-sequence(src="/resources/polygons-and-polyhedra/images/dual1/d#.png", pages="24", width="300", height="300")
    .grow: x-img-sequence(src="/resources/polygons-and-polyhedra/images/dual2/d#.png", pages="24", width="300", height="300")

The tetrahedron is dual with itself. If we were to do the same kind of
intersection, we would simply get two tetrahedra.

---{.gloss(archimedean))

## More on Polyhedra

__Archimedean solids__ are slightly less regular. They are like Platonic solids,
but they can consist of more than one type of regular polygon. They are named
after another ancient Greek mathematician:
[Archimedes of Syracuse](.bio(archimedes)). In total there are 13 Archimedean
solids, plus two mirror images.

// TODO Prisms and antiprisms, whose symmetry groups are the dihedral groups,
// are generally not considered to be Archimedean solids, despite meeting the
// above definition. With this restriction, there are only finitely many
// Archimedean solids. All but the elongated square gyrobicupola can be made via
// Wythoff constructions from the Platonic solids with tetrahedral, octahedral
// and icosahedral symmetry.

  .row
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/truncated-tetrahedron.gif")
      p.caption Truncated Tetrahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/cuboctahedron.gif")
      p.caption Cuboctahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/truncated-cube.gif")
      p.caption Truncated Cube
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/truncated-octahedron.gif")
      p.caption Truncated Octahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/rhombicuboctahedron.gif")
      p.caption Rhombicuboctahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/truncated-cuboctahedron.gif")
      p.caption Truncated Cuboctahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/snub-cube.gif")
      p.caption Sub Cube
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/icosidodecahedron.gif")
      p.caption Icosidodecahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/truncated-dodecahedron.gif")
      p.caption Truncated Dodecahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/truncated-icosahedron.gif")
      p.caption Truncated Icosahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/rhombicosidodecahedron.gif")
      p.caption Rhombicosidodecahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/truncated-icosidodecahedron.gif")
      p.caption Truncated Icosidodecahedron
    div(style="width: 160px")
      x-media(width="200", height="200", src="/resources/polygons-and-polyhedra/images/polyhedra/snub-dodecahedron.gif")
      p.caption Snub Dodecahedron

---

Plato was wrong in believing that matter consists of Platonic solids. But
regular polyhedra have many special properties that make them appear everywhere
in nature – and we can copy these properties in science and engineering.

### Viruses and Bacteria

  .row
    div(style="width: 180px")
      x-media(lightbox, width="180", height="180", src="/resources/polygons-and-polyhedra/images/radiolaria.jpg")
      p.caption Radiolaria skeleton
    div(style="width: 180px")
      x-media(lightbox, width="180", height="180", src="/resources/polygons-and-polyhedra/images/virus.jpg")
      p.caption Icosahedral virus
    .grow
      p Many viruses, bacteria and other tiny organisms are shaped like icosahedra. Viruses, for example, must enclose their genetic material inside a shell of many identical protein units. The icosahedron is the most efficient way to do this – because it consists of a few regular elements but is almost shaped like a sphere.

---

### Molecules

  .row
    div(style="width: 180px")
      x-media(lightbox, credit="NASA/JPL", width="180", height="180", src="/resources/polygons-and-polyhedra/images/buckyball.jpg")
      p.caption Buckyball molecule
    div(style="width: 180px")
      x-media(lightbox, credit="Philipp Hienstorfer, via Wikipedia", width="180", height="180", src="/resources/polygons-and-polyhedra/images/biosphere.jpg")
      p.caption Montreal Biosphere
    .grow
      p Many molecules are shaped like regular polyhedra. The most famous example is C#[sub 60] which consists of 60 carbon atoms arranged in the shape of a #[em truncated icosahedron]. It was discovered in 1985 when scientists researched interstellar dust. They named it “Buckyball” (or Buckminsterfullerene) after the architect Buckminster Fuller, famous for constructing similar-looking geodesic domes.

---

### Crystals

  .row
    div(style="width: 180px")
      x-media(lightbox, credit="Chris Gladis, via Wikipedia", width="180", height="180", src="/resources/polygons-and-polyhedra/images/crystal.jpg")
      p.caption Fluorite octahedron
    div(style="width: 180px")
      x-media(lightbox, credit="Archaeodontosaurus, via Wikipedia", width="180", height="180", src="/resources/polygons-and-polyhedra/images/rock.jpg")
      p.caption Pyrite cube
    .grow
      p Most crystals have their atoms arranged in a regular grids consisting of tetrahedra, cubes, octahedra and many other polyhedra. When they crack or shatter, you can see these patterns on a much larger scale.

---

### Construction

  .row
    div(style="width: 180px")
      x-media(lightbox, credit="Andrew Dunn, via Wikipedia", width="180", height="180", src="/resources/polygons-and-polyhedra/images/space-frame.jpg")
      p.caption Octagonal Space Frames
    div(style="width: 180px")
      x-media(lightbox, credit="© Depositphotos, anyaberkut", width="180", height="180", src="/resources/polygons-and-polyhedra/images/louvre.jpg")
      p.caption Louvre museum in Paris
    .grow
      p Tetrahedra and Octahedra are incredibly rigid and stable, which makes them very useful in construction. #[em Space frames] are polygonal structures that can support large roos and heavy bridges.

---

### Games

  .row
    div(style="width: 180px")
      x-media(lightbox, credit="© Depositphotos / ssuaphoto", width="180", height="180", src="/resources/polygons-and-polyhedra/images/football.jpg")
      p.caption Football
    div(style="width: 180px")
      x-media(lightbox, credit="© Depositphotos / blackregis2", width="180", height="180", src="/resources/polygons-and-polyhedra/images/dice.jpg")
      p.caption Polygonal role-playing dice
    .grow
      p Because of their symmetry, Platonic solids are often used to create dice. Every side has the probability of landing facing up, so the dice are always fair.
      p The truncated icosahedron is probably the most famous polyhedron in the world: it is the shape of the football.
      // TODO Rubicks cube


================================================================================

// TODO Cross Sections of 3D Solids