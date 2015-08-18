Installing ColorSchemeEditor
============================
.. code ::

    cd "${HOME}/.config/sublime-text-2/Packages"
    git clone https://github.com/facelessuser/ColorSchemeEditor.git

Instructions for installing the GUI editor for ColorSchemeEditor
===============================================================

.. code ::

    # install wxpython
    sudo apt-get install python-wxgtk2.8
    # clone repo
    cd "${HOME}/.config/sublime-text-2/Packages/User/subclrschm/subclrschm-bin-linux"
    git clone https://github.com/facelessuser/subclrschm.git subclrschm.repo
    # create a virtualenv, and install the subclrschm in it
    cd subclrschm.repo
    python2.7 <path to virtualenv>/virtualenv.py _env27
    _env27/bin/pip install -e .
    # symlink wxpython from system packages
    ln -s /usr/lib/python2.7/dist-packages/wx-2.8-gtk2-unicode  ./_env27/lib/python2.7/site-packages/
    ln -s /usr/lib/python2.7/dist-packages/wx-2.8-gtk2-unicode  ./_env27/lib/python2.7/site-packages/
    ln -s /usr/lib/python2.7/dist-packages/wxversion.py ./_env27/lib/python2.7/site-packages/
    ln -s /usr/lib/python2.7/dist-packages/wx.pth ./_env27/lib/python2.7/site-packages/
    # remove the subclrschm binary and symlink it to the entrypoint in the virtualenv
    cd ..
    rm -rf subclrschm
    ln -s subclrschm.repo/_env27/bin/subclrschm subclrschm
