# -utl-monarch-and-altair-personal-slc-creating-and-converting-pdf-tables-to-text
Monarch and altair personal slc creating and converting pdf tables to text
    %let pgm=utl-monarch-and-altair-personal-slc-creating-and-converting-pdf-tables-to-text;

    %stop_submission;

    Monarch and altair personal slc creating and converting pdf tables to text

    Too long to post here, see github

    github
    https://github.com/rogerjdeangelis/-utl-monarch-and-altair-personal-slc-creating-and-converting-pdf-tables-to-text

      CONTENTS
        1 xlc r pdf to text (english corpus)
        2 related repos

    community.altair
    https://community.altair.com/discussion/6304/monarch-10-5-will-not-import-or-export-pdf-documents?tab=all&utm_source=community-search&utm_medium=organic-search&utm_term=monarch


    PDFGEAR (always create a restore point before dweb downloads)
    Excellent free 'acrobat pro?'
    https://www.pdfgear.com
    https://www.pdfgear.com/windows-user-guide/download-install-pdfgear-on-windows.htm

    github
    https://github.com/rogerjdeangelis/utl-forever-free-for-now-pdfgear-edit-split-combine-delete-pages-substitute-for-acrobat-pro

    /*                   _
    (_)_ __  _ __  _   _| |_
    | | `_ \| `_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    */

    d:/pdf/class.pdf

    Obs    NAME       SEX    AGE    HEIGHT    WEIGHT
    ------------------------------------------------
      1    Alfred      M      14     69.0      112.5

      2    Alice       F      13     56.5       84.0

      3    Barbara     F      13     65.3       98.0

      4    Carol       F      14     62.8      102.5

      5    Henry       M      14     63.5      102.5

    data have;
     informat
       NAME $8.
       SEX $1.
       AGE 8.
       HEIGHT 8.
       WEIGHT 8.;
    input
      NAME SEX AGE HEIGHT WEIGHT;
    cards4;
    Alfred M 14 69 112.5
    Alice F 13 56.5 84
    Barbara F 13 65.3 98
    Carol F 14 62.8 102.5
    Henry M 14 63.5 102.5
    ;;;;
    run;quit;

    %utlfkil(d:/pdf/class.pdf);

    ods pdf file="d:/pdf/class.pdf" style=monospace;
    proc print data=have;
    run;quit;
    ods pdf close;

    /*       _
    / |  ___| | ___   _ __
    | | / __| |/ __| | `__|
    | | \__ \ | (__  | |
    |_| |___/_|\___| |_|

    */

    &_init_;
    proc r;
    submit;
    library(tm);
    library(pdftools);
    file<-'d:/pdf/class.pdf';
    Rpdf<-readPDF(
      control=list(text='-layout'));
    corpus<-VCorpus(URISource(file),
    readerControl=list(reader=Rpdf));
    want<-content(content(corpus)[[1]]);
    write(want,file='d:/txt/class.txt');
    lines<-unlist(strsplit(want,'\n'));
    non_empty_lines<-
      lines[!grepl('^\\s*$',lines)];
    write(non_empty_lines
      ,file='d:/txt/table.txt');
    endsubmit;
    run;quit;

    OUTPUT
    ======

    d:/txt/table.txt

    Obs NAME     SEX AGE HEIGHT WEIGHT
      1 Alfred   M    14   69.0   112.5
      2 Alice    F    13   56.5    84.0
      3 Barbara F     13   65.3    98.0
      4 Carol    F    14   62.8   102.5
      5 Henry    M    14   63.5   102.5


    Convert to sas table;

    data table;
      infile "d:/txt/table.txt" firstobs=3;
      input name & $ sex$ & age & height & weight;
    run;quit;

     Variables in Creation Order

    #    Variable    Type    Len

    1    NAME        Char      8
    2    SEX         Char      8
    3    AGE         Num       8
    4    HEIGHT      Num       8
    5    WEIGHT      Num       8

    /*___
    |___ \   _ __ ___ _ __   ___  ___
      __) | | `__/ _ \ `_ \ / _ \/ __|
     / __/  | | |  __/ |_) | (_) \__ \
    |_____| |_|  \___| .__/ \___/|___/
                     |_|
    */
    REPO
    ----------------------------------------------------------------------------------------------------------------------------------
    https://github.com/rogerjdeangelis/utl-adding-a-password-to-your-pdf-sas--free-forever-pdfgear-python
    https://github.com/rogerjdeangelis/utl-convert-pdf-to-text-using-python-and-r
    https://github.com/rogerjdeangelis/utl-create-a-pdf-excel-html-proc-report-with-greek-letters
    https://github.com/rogerjdeangelis/utl-create-a-simple-n-percent-clinical-table-in-r-sas-wps-python-output-pdf-rtf-xlsx-html-list
    https://github.com/rogerjdeangelis/utl-create-mutiple-pdf-files-from-one-table-dosubl-ods-newfile-option
    https://github.com/rogerjdeangelis/utl-creating-identical-pdf-and-powerpoint-slides
    https://github.com/rogerjdeangelis/utl-example-rtf-excel-and-pdf-reports-using-all-sas-provided-style-templates
    https://github.com/rogerjdeangelis/utl-fit-a-beta-pdf-using-sas-nlmixed-and-r-fitdistplus-package
    https://github.com/rogerjdeangelis/utl-forever-free-for-now-pdfgear-edit-split-combine-delete-pages-substitute-for-acrobat-pro
    https://github.com/rogerjdeangelis/utl-formatting-ai-seacrh-output-in-pdf-rtf-and-excel-format-perplexity-chatGPT-results
    https://github.com/rogerjdeangelis/utl-identical-side-by-side-text-and-graphics-in-pdf-and-powerpoint
    https://github.com/rogerjdeangelis/utl-mle-symbolic-solution-for-mu-and-sigma-of-normal-pdf-using-sympy
    https://github.com/rogerjdeangelis/utl-overlaying-histograms-and-scatterplots-in-powerpoint-pdf-and-jpeg
    https://github.com/rogerjdeangelis/utl-putting-a-frame-around-text-in-doc-rtf-and-pdf-ods-destinations-with-and-without-layout
    https://github.com/rogerjdeangelis/utl-r-creating-a-clinical-summary-report-in-pdf-and-txt-with-p-values
    https://github.com/rogerjdeangelis/utl-r-one-liner-scatter-plot-with-densities-along-vertical-and-horizontal-axes-in-pdf-and-ppt
    https://github.com/rogerjdeangelis/utl-removing-unwanted-bookmarks-in-pdf-table-of-contents-toc
    https://github.com/rogerjdeangelis/utl-sas-and-r-macro-to-convert-pdf-to-text
    https://github.com/rogerjdeangelis/utl-sas-ods-bidirectional-hyperlinked-table-of-contents-in-ods-pdf-html-and-excel
    https://github.com/rogerjdeangelis/utl-sas-ods-underlining-text-in-html-pdf-and-rtf
    https://github.com/rogerjdeangelis/utl-scraping-pdf-output-for-pdf-tables-and-lists
    https://github.com/rogerjdeangelis/utl-search-all-pdfs-for-an-arbitrary-word-in-mutuiple-pdf-file
    https://github.com/rogerjdeangelis/utl-side-by-side-proc-report-output-in-pdf-html-and-excel
    https://github.com/rogerjdeangelis/utl-simple-three-letter-commands-to-format-perplexity-AI-results-for-word-pdf-text-and-excel
    https://github.com/rogerjdeangelis/utl-sympy-exact-pdf-and-cdf-for-the-correlation-coefficient-given-bivariate-normals
    https://github.com/rogerjdeangelis/utl-using-beta-cdf-and-pdf-unitsquare-to-fit-non-linear-equations-and-simple-polynomials
    https://github.com/rogerjdeangelis/utl_combine_pdf_files_and_delete_pages_from_a_pdf_pyPDF_ghostscript
    https://github.com/rogerjdeangelis/utl_combining_all_pdf_files_in_a_directory
    https://github.com/rogerjdeangelis/utl_convert_pdf_tables_to_SAS_WPS_datasets
    https://github.com/rogerjdeangelis/utl_convert_pdf_tables_to_sas_tables
    https://github.com/rogerjdeangelis/utl_create-png-and-pdf-matrix-barcodes-with-embedded-url-links-r-language-graphics-plot
    https://github.com/rogerjdeangelis/utl_dropping-down-to-R-and-converting-pdfs-to-sas-tables-and-text
    https://github.com/rogerjdeangelis/utl_dropping-down-to-powershell-and-converting-doc-and-rtf-files-to-pdfs
    https://github.com/rogerjdeangelis/utl_ods_pdf_and_rtf_two_different_page_titles_on_the_same_page
    https://github.com/rogerjdeangelis/utl_pdf_graphics_top_40_a_sas_ods_graphics_look_at_chicago_public_schools_salaries_by_job
    https://github.com/rogerjdeangelis/utl_report_does_not_show_group_variable_across_new_pages_in_rtf_and_pdf

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
