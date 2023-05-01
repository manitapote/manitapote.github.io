# Resources for Deep Learning Model for dealing with multiple different languages

Different way to deal with multiple languages for comparison is to convert them into same space of embedding or to translate the multi language into one common language.

<details>
  <summary></summary>
  
  [Link]()
  
</details>

<details>
  <summary>Language-agnostic BERT Sentence Encoder (LaBSE)</summary>
  
  [Model](https://huggingface.co/setu4993/LaBSE) <br />
  [Paper](https://arxiv.org/abs/2007.01852)
  
  This model gives the embedding of multiple different languages (109 langues).
  Languages supported: <br />
  labse = {<br />
    'af': 'AFRIKAANS', <br />
    'ht': 'HAITIAN CREOLE', <br />
    'pt': 'PORTUGUESE', <br />
    'am': 'AMHARIC', <br />
    'hu': 'HUNGARIAN', <br />
    'ro': 'ROMANIAN', <br />
    'ar': 'ARABIC', <br />
    'hy': 'ARMENIAN', <br />
    'ru': 'RUSSIAN', <br />
    'as': 'ASSAMESE', <br />
    'id': 'INDONESIAN', <br />
    'rw': 'KINYARWANDA', <br />
    'az': 'AZERBAIJANI', <br />
    'ig': 'IGBO', <br />
    'si': 'SINHALESE', <br />
    'be': 'BELARUSIAN', <br />
    'is': 'ICELANDIC', <br />
    'sk': 'SLOVAK', <br />
    'bg': 'BULGARIAN', <br />
    'it': 'ITALIAN', <br />
    'sl': 'SLOVENIAN', <br />
    'bn': 'BENGALI',<br />
    'ja': 'JAPANESE',<br />
    'sm': 'SAMOAN',<br />
    'bo': 'TIBETAN',<br />
    'jv': 'JAVANESE',<br />
    'sn': 'SHONA',<br />
    'bs': 'BOSNIAN',<br />
    'ka': 'GEORGIAN',<br />
    'so': 'SOMALI',<br />
    'ca': 'CATALAN',<br />
    'kk': 'KAZAKH',<br />
    'sq': 'ALBANIAN',<br />
    'ceb': 'CEBUANO',<br />
    'km': 'KHMER',<br />
    'sr': 'SERBIAN',<br />
    'co': 'CORSICAN',<br />
    'kn': 'KANNADA',<br />
    'st': 'SESOTHO',<br />
    'cs': 'CZECH',<br />
    'ko': 'KOREAN',<br />
    'su': 'SUNDANESE',<br />
    'cy': 'WELSH',<br />
    'ku': 'KURDISH',<br />
    'sv': 'SWEDISH',<br />
    'da': 'DANISH',<br />
    'ky': 'KYRGYZ',<br />
    'sw': 'SWAHILI',<br />
    'de': 'GERMAN',<br />
    'la': 'LATIN',<br />
    'ta': 'TAMIL',<br />
    'el': 'GREEK',<br />
    'lb': 'LUXEMBOURGISH',<br />
    'te': 'TELUGU',<br />
    'en': 'ENGLISH',<br />
    'lo': 'LAOTHIAN',<br />
    'tg': 'TAJIK',<br />
    'eo': 'ESPERANTO',<br />
    'lt': 'LITHUANIAN',<br />
    'th': 'THAI',<br />
    'es': 'SPANISH',<br />
    'lv': 'LATVIAN',<br />
    'tk': 'TURKMEN',<br />
    'et': 'ESTONIAN',<br />
    'mg': 'MALAGASY',<br />
    'tl': 'TAGALOG',<br />
    'eu': 'BASQUE',<br />
    'mi': 'MAORI',<br />
    'tr': 'TURKISH',<br />
    'fa': 'PERSIAN',<br />
    'mk': 'MACEDONIAN',<br />
    'tt': 'TATAR',<br />
    'fi': 'FINNISH',<br />
    'ml': 'MALAYALAM',<br />
    'ug': 'UIGHUR',<br />
    'fr': 'FRENCH',<br />
    'mn': 'MONGOLIAN',<br />
    'uk': 'UKRAINIAN',<br />
    'fy': 'FRISIAN',<br />
    'mr' : 'MARATHI',<br />
    'ur' : 'URDU',<br />
    'ga' : 'IRISH',<br />
    'ms' : 'MALAY',<br />
    'uz' : 'UZBEK',<br />
    'gd' : 'SCOTS_GAELIC',<br />
    'mt' : 'MALTESE',<br />
    'vi' : 'VIETNAMESE',<br />
    'gl' : 'GALICIAN',<br />
    'my' : 'BURMESE',<br />
    'wo' : 'WOLOF', <br />
    'gu' : 'GUJARATI', <br />
    'ne' : 'NEPALI', <br />
    'xh' : 'XHOSA', <br />
    'ha' : 'HAUSA', <br />
    'nl' : 'DUTCH', <br />
    'yi' : 'YIDDISH', <br />
    'haw': 'HAWAIIAN', <br />
    'no' : 'NORWEGIAN', <br />
    'yo' : 'YORUBA', <br />
    'he' : 'HEBREW', <br />
    'ny' : 'NYANJA', <br />
    'zh' : 'CHINESE', <br />
    'hi' : 'HINDI', <br />
    'or' : 'ORIYA', <br />
    'zu' : 'ZULU', <br />
    'hmn': 'HMONG', <br />
    'pa' : 'PUNJABI', <br />
    'hr' : 'CROATIAN', <br />
    'pl' : 'POLISH', <br />
} <br />
  
</details>

<details>
  <summary>mBART-50</summary>
  
  [Link](https://github.com/sdhilip200/Machine-Translation-using-mBART-50-and-HuggingFace/blob/main/Machine_Translation.ipynb)
  
  [Link](https://huggingface.co/facebook/mbart-large-50-many-to-many-mmt)
  
  mBART-50 is a language translation model. This model supports 50 different languages.
  Language codes are as follows:
  
 mbart = {
'Arabic' : 'ar_AR', 
'Czech' : 'cs_CZ', 
'German' : 'de_DE',
'English': 'en_XX', 
'Spanish' : 'es_XX', 
'Estonian' : 'et_EE', 
'Finnish' : 'fi_FI', 
'French' : 'fr_XX', 
'Gujarati' : 'gu_IN', 
'Hindi': 'hi_IN', 
'Italian': 'it_IT', 
'Japanese' : 'ja_XX', 
'Kazakh' : 'kk_KZ', 
'Korean' : 'ko_KR', 
'Lithuanian' : 'lt_LT', 
'Latvian' : 'lv_LV', 
'Burmese': 'my_MM', 
'Nepali' : 'ne_NP', 
'Dutch' : 'nl_XX', 
'Romanian': 'ro_RO', 
'Russian' : 'ru_RU', 
'Sinhala' : 'si_LK', 
'Turkish' : 'tr_TR', 
'Vietnamese' : 'vi_VN', 
'Chinese': 'zh_CN', 
'Afrikaans' : 'af_ZA', 
'Azerbaijani' : 'az_AZ',
'Bengali' : 'bn_IN', 
'Persian' : 'fa_IR', 
'Hebrew' : 'he_IL', 
'Croatian' : 'hr_HR', 
'Indonesian' : 'id_ID', 
'Georgian': 'ka_GE', 
'Khmer' : 'km_KH',
'Macedonian' : 'mk_MK', 
'Malayalam' : 'ml_IN', 
'Mongolian' : 'mn_MN', 
'Marathi' : 'mr_IN', 
'Polish' : 'pl_PL', 
'Pashto' : 'ps_AF',
'Portuguese' : 'pt_XX', 
'Swedish': 'sv_SE', 
'Swahili' : 'sw_KE', 
'Tamil' : 'ta_IN', 
'Telugu' : 'te_IN',
'Thai' : 'th_TH', 
'Tagalog' : 'tl_XX', 
'Ukrainian' : 'uk_UA', 
'Urdu' : 'ur_PK', 
'Xhosa' : 'xh_ZA',
'Galician' :'gl_ES', 
'Slovene' : 'sl_SI'
}
  
</details>


