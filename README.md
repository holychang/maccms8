# maccms version <= v8
#xss
Vulnerability page：
File /template/paody/html/vod_index.html lines 6 and lines 7:
<meta name="keywords" content="{maccms:keywords}" />
<meta name="description" content="{maccms:description}" />

These function can also lead to the creation of vulnerabilities：
File /a/tpl/module/system.php lines 39-56:
	$config['site']['name'] = trim(be('post','site_name'));
	$config['site']['installdir'] = trim(be('post','site_installdir'));
	$config['site']['url'] = trim(be('post','site_url'));
	$config['site']['keywords'] = trim(be('post','site_keywords'));
	$config['site']['description'] = trim(be('post','site_description'));
	
	$config['site']['templatedir'] = trim(be('post','site_templatedir'));
	$config['site']['htmldir'] = trim(be('post','site_htmldir'));
	
	$config['site']['mobstatus'] = trim(be('post','site_mobstatus'));
	$config['site']['mobtemplatedir'] = trim(be('post','site_mobtemplatedir'));
	$config['site']['mobhtmldir'] = trim(be('post','site_mobhtmldir'));
	
	
	$config['site']['icp'] = trim(be('post','site_icp'));
	$config['site']['email'] = trim(be('post','site_email'));
	$config['site']['qq'] = trim(be('post','site_qq'));
