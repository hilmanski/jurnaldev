---
title: "Simulasi urusan administrasi di Indonesia"
date: 2021-05-05T10:28:59+08:00
description: "Sudah tahu kan bagaimana rasanya mengurus surat surat di negeri kita ini? Simulasi Mengurus dokumen di Indonesia bagaiman mengumpulkan bola naga dragon ball"
tags: ["random"]
featured_image: https://i.ibb.co/VgBxw05/Screen-Shot-2021-05-05-at-2-29-36-PM.png
slug: administrasi-indonesia
---
{{< rawhtml >}}
 <main class='adminindo'>
        <p>Dokumen yang perlu dikumpulkan: (masukkan bola ke dalam kotak)</p>
        <br>
        <ol>
            <li>Surat pengantar RT</li>
            <li>Surat pengantar RW</li>
            <li>Surat pengantar Kelurahan</li>
            <li>Surat Keterangan Kelakuan Baik</li>
            <li>Surat Keterangan Catatan Kepolisian</li>
            <li>Pas foto 3x4, 4x6</li>
            <li>Foto copy KTP, NPWP, KK, BPJS</li>
        </ol>
        
        <div id="dragonBox" style="display: none;">
            <img class="blink" id="dragon" src="https://i.ibb.co/7VWW1St/pngegg.png" draggable="true" ondragstart="drag(event)"
                width="300" height="300">
        
            <div class="speech-bubble">
                <h3>
                    HO.. HO.. HO.. SUDAH LENGKAP..
                    SILAHKAN KEMBALI LAGI..
                    SEMUANYA HARUS DILEGALISIR DAN CAP BASAH
                </h3>
            </div>
        </div>
        
        <div id="box" class="dropzone"></div>
        <br>
        <img class="drag-drop" id="ball_1" src="https://i.ibb.co/6R5ZnLc/1.png" width="40" height="40">
        <img class="drag-drop" id="ball_2" src="https://i.ibb.co/NLZrK9G/2.png" width="40" height="40">
        <img class="drag-drop" id="ball_3" src="https://i.ibb.co/hFxC1md/3.png" width="40" height="40">
        <img class="drag-drop" id="ball_4" src="https://i.ibb.co/DQfRh4w/4.png" width="40" height="40">
        <img class="drag-drop" id="ball_5" src="https://i.ibb.co/9cycX4z/5.png" width="40" height="40">
        <img class="drag-drop" id="ball_6" src="https://i.ibb.co/RHNgZPx/6.png" width="40" height="40">
        <img class="drag-drop" id="ball_7" src="https://i.ibb.co/8my1Yb0/7.png" width="40" height="40">
        
        
        <small>
            <p>Shenron image by https://www.pngegg.com/en/png-zxzfs </p>
        </small>
        
        <p>Based on:</p>
        <blockquote class="twitter-tweet">
            <p lang="in" dir="ltr">Urusan administratif Indonesia<br>Seperti mengumpulkan bola naga <a
                    href="https://t.co/Dhz8GKHjlj">pic.twitter.com/Dhz8GKHjlj</a></p>&mdash; Hilman Ramadhan ???? (@hilmanski) <a
                href="https://twitter.com/hilmanski/status/1382632708996694019?ref_src=twsrc%5Etfw">April 15, 2021</a>
        </blockquote>
        <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
        
        <script src="https://cdn.jsdelivr.net/npm/interactjs/dist/interact.min.js"></script>
        </main>
        
        <script>
            let documents = []

            interact('.dropzone').dropzone({
                // Require a 75% element overlap for a drop to be possible
                overlap: 0.75,

                // listen for drop related events:
                ondropactivate: function (event) {
                    event.target.classList.add('drop-active')
                },
                ondragenter: function (event) {
                    var draggableElement = event.relatedTarget
                    var dropzoneElement = event.target

                    // feedback the possibility of a drop
                    dropzoneElement.classList.add('drop-target')
                    draggableElement.classList.add('can-drop')
                    draggableElement.textContent = 'Dragged in'
                },
                ondragleave: function (event) {
                    // remove the drop feedback style
                    event.target.classList.remove('drop-target')
                    event.relatedTarget.classList.remove('can-drop')
                    event.relatedTarget.textContent = 'Dragged out'
                },
                ondrop: function (event) {
                    const dragged_el_id = event.relatedTarget.id

                    const nr = dragged_el_id.replace('ball_', '')
                    updateDocList(nr)
                    // event.relatedTarget.textContent = 'Dropped'
                },
                ondropdeactivate: function (event) {
                    // remove active dropzone feedback
                    event.target.classList.remove('drop-active')
                    event.target.classList.remove('drop-target')
                }
            })

            interact('.drag-drop')
                .draggable({
                    inertia: true,
                    modifiers: [
                        interact.modifiers.restrictRect({
                            restriction: 'parent',
                            endOnly: true
                        })
                    ],
                    autoScroll: true,
                    // dragMoveListener from the dragging demo above
                    listeners: { move: dragMoveListener }
                })

            function dragMoveListener(event) {
                var target = event.target
                // keep the dragged position in the data-x/data-y attributes
                var x = (parseFloat(target.getAttribute('data-x')) || 0) + event.dx
                var y = (parseFloat(target.getAttribute('data-y')) || 0) + event.dy

                // translate the element
                target.style.transform = 'translate(' + x + 'px, ' + y + 'px)'

                // update the posiion attributes
                target.setAttribute('data-x', x)
                target.setAttribute('data-y', y)
            }

            function updateDocList(nr) {
                const lists = document.getElementsByTagName('li')
                const index = nr - 1
                lists[index].style.textDecoration = "line-through"
                documents.push(index)

                if (documents.length == 7)
                    callDragon()
            }

            function callDragon() {
                document.getElementsByTagName('ol')[0].style.display = "none"
                document.getElementById('dragonBox').style.display = "block"
                document.getElementById('body').style.background = "black"
                document.getElementById('box').style.display = "none"
            }
        </script>
        
        <style>
            .adminindo a {
                font-size: 1.5rem;
                text-decoration: underline;
                color: rgb(40, 40, 40);
            }
        
            .blink {
                animation: blink-animation 0.5s steps(5, start) infinite;
                -webkit-animation: blink-animation 0.5s steps(5, start) infinite;
            }
        
            @keyframes blink-animation {
                to {
                    visibility: hidden;
                }
            }
        
            @-webkit-keyframes blink-animation {
                to {
                    visibility: hidden;
                }
            }
        
            #dragonBox {
                position: relative;
            }
        
            #dragonBox .speech-bubble {
                position: absolute;
                left: 50px;
                top: -100px;
            }
        
            .speech-bubble {
                position: relative;
                background: #4fee61;
                border-radius: .4em;
                padding: 5px 10px;
                width: 300px;
        
            }
        
            .speech-bubble:after {
                content: '';
                position: absolute;
                bottom: 0;
                left: 50%;
                width: 0;
                height: 0;
                border: 20px solid transparent;
                border-top-color: #4fee61;
                border-bottom: 0;
                border-left: 0;
                margin-left: -10px;
                margin-bottom: -20px;
            }
        
            .can-drop {
                border-color: yellow;
            }
        
            .dropzone {
                border: dashed 4px transparent;
                height: 80px;
                width: 300px;
                background-color: antiquewhite;
            }
        
            .drop-active {
                border: 1px solid orange;
            }

            img {
                display: inline-block;
            }
        
            img:hover {
                cursor: -webkit-grab !important;
                cursor: grab !important;
            }
        </style>
</main>
{{< /rawhtml >}}